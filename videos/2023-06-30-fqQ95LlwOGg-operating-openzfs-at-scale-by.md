---
record_id: "youtube:fqQ95LlwOGg"
video_id: fqQ95LlwOGg
title: Operating OpenZFS at Scale by Satabdi Das
channel: OpenZFS
url: "https://www.youtube.com/watch?v=fqQ95LlwOGg"
watched_date: 2023-06-30
watched_at: "2023-06-30T12:00:00Z"
watch_count: 1
duration_seconds: 2281
source: youtube-history-browser
added_date: 
history_label: Jun 30, 2023
history_order: 136
watched_at_precision: date-from-history-label
watched_percent: 100
estimated_watched_seconds: 2281
transcript_status: fetched
transcript_content_hash: f29615a9bc220b54b969d99e96cd92a162a3385f89a0267e433edb1bcddb9756
analysis_mode: health
summary_source: local
model_source: local
summary_status: ready
item_status: ready
wealth_eligible: false
summary_model: Qwen3.8-Flash-Next-UD-Q4_K_XL
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Satabdi Das, an AWS software development engineer, described AWS FSx for OpenZFS, a fully managed OpenZFS file service launched in December 2021 and built on AWS Graviton/ARM, exposing FSx volumes over NFS v3, v4.1, and v4.2. She covered architecture (file server plus storage disks, ARC cache, volumes as datasets, file system as collection of volumes), management APIs/CLI/SDK for creating and scaling storage and throughput, snapshots, backups, quotas, compression, record size, NFS exports, maintenance windows, patching, encryption at rest with KMS and in transit, CloudWatch metrics retained 15 months, and operational monitoring/mitigation. Key claims included up to 12.5 GB/s throughput and 1 million IOPS from ARC, 100–200 microsecond latencies, up to 4 GB/s and 160k disk IOPS, network I/O about three times faster than disk I/O, compression improving read throughput (roughly provisioned throughput times compression ratio, e.g., 8–12 GB/s at 4 GB/s with 2–3x ZSTD), throughput scaling increasing ARC size, and customer examples: Vela Games using snapshots/cloning for build checkpointing with a reported 60% build-time improvement, and Rev.com reducing operating costs nearly 30% while accelerating ML training. Q&A added that AWS uses its own encryption below ZFS rather than native ZFS encryption, AWS-internal backup infrastructure rather than ZFS send/receive, kernel NFS, no L2ARC/SLOG offered, and a desire for native ZFS metadata statistics for operations such as open, close, mknod, mkdir, getattr, setattr, link, and unlink.

No health implications; the actionable items are technical: evaluate FSx for OpenZFS when you want managed NFS/ZFS without self-managing hardware, patching, backups, or deep ZFS tuning, then prototype a small volume, benchmark compression (LZ4/ZSTD) on read-heavy data, test record size against workload, and scale throughput deliberately because higher throughput also enlarges ARC and can help metadata-intensive workloads. Use CloudWatch metrics (read/write operations, storage used, compression ratio, CPU/memory) to validate performance, set maintenance/backup windows, review the default seven-day backup retention, and use snapshots/clones for CI, test environments, or rapid recovery. Follow-up questions should cover exact encryption implementation, backup internals and restore SLAs, whether L2ARC/SLOG or other ZFS tuning will be exposed, metadata-statistics availability (including possible eBPF/ZFS instrumentation), NFS client compatibility including Windows, ARM-specific bugs/upstream fixes, and cost/performance comparisons against self-managed OpenZFS or other AWS file services.

## Transcript

[00:00:04] foreign
[00:00:09] I'm a software development engineer at
[00:00:13] AWS FSX part of ncfs and today I'm going
[00:00:18] to give you a peek into
[00:00:20] what is AWS FSX for opencfs
[00:00:27] um
[00:00:27] before I start just a quick show of
[00:00:31] hands how many of you have heard about
[00:00:33] AWS FSX
[00:00:36] oh that's that's a good number so I
[00:00:38] don't have to spend a lot of time for
[00:00:39] those who do not know it yet
[00:00:41] um AWS FSX offers file system in Cloud
[00:00:44] the x is literally your choice for your
[00:00:48] workload
[00:00:51] um
[00:00:52] it AWS FSX offers four engines uh
[00:00:56] Windows file server FSC AWS FSX or
[00:00:59] Windows file server uh AWS FSX for
[00:01:03] luster uh FSX for NADA pound Tab and we
[00:01:07] G8
[00:01:09] um if a 64 open ZFS we launched FSX for
[00:01:12] open CFS in December 2021.
[00:01:17] what is FSX for opencfs it's a storage
[00:01:20] service that lets you launch run and
[00:01:24] scale fully managed opencfs file systems
[00:01:27] on AWS it provides the familiar features
[00:01:30] performance and capabilities of opencfs
[00:01:33] file systems with the agility and
[00:01:36] scalability and simplicity that you can
[00:01:39] expect from a fully managed AWS service
[00:01:43] it is built on AWS graviton processor
[00:01:46] which are based on 64-bit arm
[00:01:49] architecture and customers can access
[00:01:52] either FSX for opencfs file systems over
[00:01:56] NFS protocols we support uh V3 for 4.1
[00:02:01] and 4.2
[00:02:05] um before I dive deeper into our
[00:02:09] services I just wanted to call out
[00:02:11] um what are the resources
[00:02:13] that we manage
[00:02:16] um so we manage we have something called
[00:02:19] the physics volume which you may know as
[00:02:23] um opencfs dataset file system we call
[00:02:26] it volume because
[00:02:29] um many of our customers do not actually
[00:02:31] know about opencfs they are not opencfs
[00:02:35] Savvy users all they care about uh cost
[00:02:39] effective file system and they also care
[00:02:43] about the uniformity of the terms that
[00:02:46] we use across AWS service and we do use
[00:02:49] FSX volume for other file engines
[00:02:52] if it's like snapshot is opencfs
[00:02:55] Snapshot no surprise there and what you
[00:02:58] call an FSX opencfs file system is a
[00:03:02] collection of the FSX volumes
[00:03:08] why do customers use FSX for opencfs and
[00:03:11] this is just a
[00:03:14] summary of the reasons that customers
[00:03:17] use and I'm going to dive deeper into
[00:03:19] each of them uh the first one being it's
[00:03:22] high performance and
[00:03:25] it offers Advanced ZFS capabilities and
[00:03:29] it is cost effective
[00:03:34] now before we talk about performance
[00:03:37] um we I would like to explain how data
[00:03:41] is accessed from an FSX opencfs file
[00:03:45] system
[00:03:46] so the clients access the file system
[00:03:48] from inside AWS cloud
[00:03:52] and each FSX file system consists of a
[00:03:56] file server attached to storage disks
[00:04:01] um fsx4 open ZFS uses the arc cache
[00:04:05] which improves the access to the portion
[00:04:08] of data that can be driven from the in
[00:04:11] memory cache and fs64 opencfs file
[00:04:15] systems can serve Network i o about
[00:04:18] three times faster than the disk IO
[00:04:22] so customers can drive greater
[00:04:25] throughput iops with much lower
[00:04:28] latencies for frequently access data in
[00:04:32] Cache
[00:04:36] if a 64 open CFS supports up to 12.5
[00:04:39] gigabyte per second throughput and 1
[00:04:42] million iops when the data is accessed
[00:04:46] from in memory and the latencies can go
[00:04:50] as low as 100 to 200 microseconds
[00:04:56] for data accessed from the persistent
[00:04:59] disk storage we offer up to four
[00:05:03] gigabytes per second throughput and 160k
[00:05:06] disk iops and this level of performance
[00:05:10] is possible because of two reasons one
[00:05:13] of course because of the underlying
[00:05:15] Hardware supports this level of uh
[00:05:17] throughput or latencies but also because
[00:05:21] of Advanced ZFS capabilities that you
[00:05:23] use for example Arc or or compression
[00:05:31] um customers use FSX opencfs file
[00:05:34] systems because of the ease of use
[00:05:38] um
[00:05:38] a customer can create an opencfs file
[00:05:41] systems in a matter of minutes they can
[00:05:43] use the CLI the API the SDK and they can
[00:05:47] create a file system they can scale it
[00:05:50] up uh the storage of the file system
[00:05:52] they can scale up the throughput of the
[00:05:54] file system just in a matter of minutes
[00:05:56] now if you compare that experience with
[00:05:59] creating an opencfs file system where
[00:06:01] you have to provision your Hardware you
[00:06:04] have to install the software you'll have
[00:06:06] to upgrade it regularly you have to
[00:06:09] patch against vulnerabilities you have
[00:06:11] to manage your own backup
[00:06:13] all those complexity uh are taken care
[00:06:18] of by by the service
[00:06:24] I wanted to give you an example of how a
[00:06:26] customer can create a file system just
[00:06:28] to uh given sort of a just to give an
[00:06:33] idea how easy it is this is a an API the
[00:06:37] CLI basically using which customer can
[00:06:40] create 400 gigabyte file system
[00:06:44] where they give the deployment type
[00:06:46] which is an interlearn internal way of
[00:06:49] us
[00:06:51] saying which kind of file system of
[00:06:54] opencfs we are going to provision right
[00:06:56] now we only support single lazy one and
[00:06:59] then they can create a 128 throughput
[00:07:02] capacity file system
[00:07:09] um
[00:07:10] we also offer apis for creating volumes
[00:07:15] FSX volumes creating snapshots creating
[00:07:18] backups they can update the file system
[00:07:20] storage they can update the file system
[00:07:22] throughput capacity uh they can update
[00:07:24] the volume configurations for example
[00:07:26] they can update the quota the
[00:07:28] compression and the NFS exports the
[00:07:32] record size all using native FSX API
[00:07:39] many customers prefer to scale up uh
[00:07:42] automate their scaling operations when
[00:07:44] they cross a certain threshold and they
[00:07:46] can use uh Native AWS apis to achieve
[00:07:50] that
[00:07:54] um it's also fully managed what do I
[00:07:56] mean by fully managed is we patch uh
[00:07:59] regularly the file systems we take
[00:08:02] periodic incremental backups and we also
[00:08:05] offer data encryption let's go a little
[00:08:08] bit deeper into each of those fields
[00:08:11] um we patch file system regularly during
[00:08:14] maintenance Windows what do we patch we
[00:08:16] upgrade the software running on the file
[00:08:19] server and the day and the week and the
[00:08:22] time can be decided by the customer and
[00:08:24] they can also update those maintenance
[00:08:26] windows
[00:08:27] and
[00:08:29] we uh
[00:08:31] we take opencfs release versions and
[00:08:35] then we review within our team we have a
[00:08:38] process around that and then we based on
[00:08:39] our review we decide which version to to
[00:08:42] get and to patch into our file systems
[00:08:50] uh we also offer data protection and
[00:08:53] there are two ways customer can get data
[00:08:57] protection
[00:08:58] um one is they can use FSX opencfs
[00:09:03] snapshots by using that they can easily
[00:09:08] undo file changes and compare file
[00:09:10] versions go back to an older version if
[00:09:13] they have uh they have made any mistake
[00:09:16] and the other option is FSX opencfs
[00:09:19] backup which is a point in time image of
[00:09:22] the whole file system
[00:09:26] what is fsx4 open ZFS backup so it's
[00:09:28] incremental in nature we use
[00:09:32] um internal AWS infrastructure to take
[00:09:34] the backup and it is highly durable we
[00:09:37] store those snapshots in S3 Amazon S3 it
[00:09:42] is file system consistent meaning you
[00:09:45] can create a file system from any of
[00:09:49] those backups
[00:09:50] when do we take it we have an automated
[00:09:53] job that takes daily backups it is taken
[00:09:56] during backup window again we give
[00:09:58] customer the choice if they want to
[00:10:00] change the backup window or not they can
[00:10:02] also modify the retention period the
[00:10:04] default is seven days they can change it
[00:10:07] up to a certain threshold and there is
[00:10:10] no availability hit when they are taking
[00:10:12] the backup
[00:10:16] we also offer data encryption uh there
[00:10:19] are two types of encryption that we
[00:10:21] offer encryption at rest encryption in
[00:10:23] transit
[00:10:24] encryption at rest means customers data
[00:10:27] is protected and encrypted using IF
[00:10:31] customers provide a key using AWS Key
[00:10:34] Management Service which is another
[00:10:36] service for Key Management we encrypt
[00:10:38] the data using customers key
[00:10:40] and when data and metadata is encrypted
[00:10:43] it will be encrypted before written
[00:10:46] before being written to the file system
[00:10:48] and when it is presented back to the
[00:10:50] application it will be decrypted before
[00:10:52] presenting back to the applications
[00:10:55] um encryption in transit is offered when
[00:10:58] the clients access the data from an
[00:11:01] Amazon ec2 instance that support
[00:11:03] encryption in transit
[00:11:08] now how do we operate FSX for opencfs
[00:11:12] um we measure uh before uh monitoring
[00:11:17] and then we monitor what we measured and
[00:11:20] if there is any
[00:11:22] health file server degraded file server
[00:11:25] Health we mitigate let's go a little bit
[00:11:27] deeper into each of them
[00:11:30] we share metrics with the customers
[00:11:32] um so that they themselves can monitor
[00:11:35] their file system performance
[00:11:37] um we retain these metrics for uh 15
[00:11:41] months so that customer can have a have
[00:11:43] a historical view of how their file
[00:11:46] system has performed over time we offer
[00:11:49] customers read operations and write
[00:11:50] operations uh amount of storage they
[00:11:53] have used What is the compression ratio
[00:11:55] they have achieved so far and the CPU
[00:11:58] and memory usage of the filed server
[00:12:01] we send this data to
[00:12:04] AWS cloudwatch by we I mean Amazon FSX
[00:12:08] for opencfs sends those metrics
[00:12:11] Jefferson to AWS cloudwatch at one
[00:12:14] minute intervals and customers can
[00:12:17] access those metrics from AWS cloudwatch
[00:12:20] which is another service AWS offers for
[00:12:24] monitoring
[00:12:27] we augment the file server metrics with
[00:12:31] the metrics that we Source from CFS
[00:12:34] along with this metrics we continuously
[00:12:37] monitor the file systems and generate
[00:12:40] internal alarms for us and we generate
[00:12:44] dashboards which we regularly review by
[00:12:48] regularly women we review them daily
[00:12:51] and among many other things we monitor
[00:12:54] file server Health the state of the
[00:12:56] software running on the service or
[00:12:58] running on the server and
[00:13:01] we operate what we build so by that I
[00:13:05] mean our team writes the code deploys it
[00:13:08] in production and we operate our code so
[00:13:12] we put a lot of uh effort into how we
[00:13:15] monitor our file system health and how
[00:13:18] we monitor the whole health of the
[00:13:21] service and how we automate uh how we
[00:13:24] can automate mitigations
[00:13:31] um
[00:13:32] so I've uh
[00:13:38] I think I missed something yeah
[00:13:40] now how do we how do customers use FSX
[00:13:44] for opencfs
[00:13:47] they can tune uh a few aspects of their
[00:13:52] file system for example they can tune
[00:13:55] the record size we offer 128 QB byte
[00:13:58] Cricket size and our public
[00:14:00] documentation maintains that that is
[00:14:02] sufficient that is good enough for most
[00:14:04] of the workload but customers can choose
[00:14:07] to update their Wicket size based on
[00:14:10] their workload
[00:14:12] um they can also change the compression
[00:14:14] type we support lt4 Z standard and no
[00:14:18] compression
[00:14:20] um and many of our customers use the STD
[00:14:22] uh and lc4 and no compression there's a
[00:14:25] good mix of each of these
[00:14:27] they can also change the user and clip
[00:14:30] quota uh based on their requirement and
[00:14:33] all of this they can access uh from the
[00:14:36] API
[00:14:40] so what did we learn so far uh we we
[00:14:45] launched the service as I mentioned in
[00:14:46] December 2021 so it's been almost a year
[00:14:50] we have been operating and we have a few
[00:14:52] uh learnings that we can share with you
[00:14:55] so one is we know compression is good
[00:14:58] for saving this disk space but we also
[00:15:03] noticed that for read heavy workloads
[00:15:06] compression can significantly improve uh
[00:15:09] the overall throughput performance of
[00:15:11] the file system because it reduces the
[00:15:13] amount of data that needs to be accessed
[00:15:16] it needs to be sent between the
[00:15:18] underlying storage and the file server
[00:15:21] the effective throughput is actually
[00:15:24] roughly equivalent to the product of the
[00:15:27] provisioned disk throughput and the the
[00:15:30] level of compression ratio for example
[00:15:34] um for 4 KB byte throughput which is our
[00:15:37] highest throughput level that we offer
[00:15:39] currently and if you if the STD
[00:15:41] compression
[00:15:43] ratio is around 2 to 3x the read
[00:15:46] throughput is is by around 8 to 12
[00:15:50] gigabyte per second
[00:15:56] we also learned that there's a
[00:15:58] relationship between throughput and Arc
[00:16:00] this was by Design but this is something
[00:16:02] which we sort of learned as we operate
[00:16:05] and I wanted to share with you
[00:16:07] um the file systems throughput uh
[00:16:10] actually uh determines the size of Arc
[00:16:13] so when a customer increases their
[00:16:15] throughput
[00:16:16] um it improves the file system
[00:16:18] performance in two ways one it increases
[00:16:22] the throughput and the iops customers
[00:16:24] can derive from the disk
[00:16:26] but since the arc size also increases it
[00:16:31] is also a good fit for a workload with
[00:16:35] larger workloads
[00:16:37] uh for example some metadata intensive
[00:16:40] workloads will benefit from a larger
[00:16:42] server which has uh larger in memory
[00:16:46] cache
[00:16:51] we leverage Arc tunings to improve uh
[00:16:55] file system performance and stability
[00:16:57] and since Arc works so well for the
[00:17:00] customers we want to maximize the amount
[00:17:03] of memory we give to Arc
[00:17:05] but on smaller servers we noticed that
[00:17:09] certain metadata intensive workloads can
[00:17:12] push the arc size well above what we
[00:17:15] configured for ZFS Arc Max and the
[00:17:19] amount of memory
[00:17:21] free memory also gets pushed below the
[00:17:25] ZFS Arc sys3 so he experimented with a
[00:17:29] few few tunings that we use to for using
[00:17:34] the pruning and Arch eviction strategy
[00:17:36] we use our stats so thank you for
[00:17:39] writing the Tool uh that helped us debug
[00:17:42] like how we can solve this and how we
[00:17:45] can Elevate the memory pressure and we
[00:17:48] we made tunings in in Arches free and
[00:17:51] art made a strategy to
[00:17:53] basically balance
[00:17:55] um uh performance versus stability in a
[00:17:58] way so that
[00:18:00] it helps the file improve the file
[00:18:02] system health
[00:18:07] we also learned that many of our
[00:18:09] customers are actually as I mentioned
[00:18:10] before are actually not ZFS heavy users
[00:18:13] they all need a file system which is
[00:18:15] cheap which is highly performant and
[00:18:19] that we pre-tune their file systems they
[00:18:22] do not have to worry about how to tune
[00:18:26] different ZFS components they can just
[00:18:28] use it as it is out of the box and it
[00:18:32] works for most of them many customers
[00:18:34] use it as general purpose storage not
[00:18:37] even HPC workload they use it as home
[00:18:40] directories for storing their binaries
[00:18:42] and it is cost effective
[00:18:48] um we also learned that for many
[00:18:51] customers that use metadata intensive
[00:18:55] workload they would be greatly highly
[00:19:00] helped if they have access to metadata
[00:19:02] statistics so and right now we do not
[00:19:05] have a clear path to Source those
[00:19:08] metadata statistics from ZFS
[00:19:11] um what we are looking for we're looking
[00:19:12] for metadata statistics on open close
[00:19:15] mcnode mcdir get address say that or get
[00:19:19] Etc Link and Link we have a list of
[00:19:21] operations that we want to if possible
[00:19:23] uh to Source metadata from ZFS and we
[00:19:28] hope we can contribute in some way to
[00:19:30] the community if we can get those uh
[00:19:33] statistics from CFS natively
[00:19:39] um I also wanted to give you a peek into
[00:19:41] what are the different customer use
[00:19:42] cases that you have seen so far uh I'll
[00:19:45] not spend uh too much time on this slide
[00:19:48] because I'm going to go into each of
[00:19:50] this category in the next few slides
[00:19:55] so many customers use opencfs for high
[00:19:59] performance storage for latency
[00:20:01] sensitive and iops intensive use cases
[00:20:04] many customers in financial analyzes uh
[00:20:08] front-end Eda by front end Eda they mean
[00:20:10] simulation of of designs genomics
[00:20:15] research basically where they would care
[00:20:19] for low latency High throughput features
[00:20:24] of a file system they use opencfs
[00:20:26] uh many customers also use streaming
[00:20:28] video processing
[00:20:31] um because
[00:20:32] of the same reasons that are mentioned
[00:20:34] at the right side right hand side of the
[00:20:36] slide uh because of the latencies and
[00:20:38] the iops and the throughput
[00:20:40] um and the low cost of course
[00:20:46] sound and get you a little more sound
[00:20:48] this is not live for now
[00:20:50] was I not Audible it's
[00:20:53] the system is not working oh are you
[00:20:56] guys did you all hear me or okay good
[00:21:01] um
[00:21:02] where was I okay so many other customer
[00:21:05] use cases are it can be a drop it can be
[00:21:09] used as a drop in replacement for
[00:21:11] self-managed NFS as I mentioned before
[00:21:15] customers use as a user share home
[00:21:17] directory uh simple storage uh because
[00:21:20] it's uh because of the cost and the
[00:21:22] flexible storage and triple provisioning
[00:21:24] what do I mean by flexible storage so
[00:21:26] basically as I mentioned it's so very
[00:21:29] easy to increase the storage of your
[00:21:31] file systems the increase the throughput
[00:21:32] of your file system just without
[00:21:34] thinking of how do I uh like configure
[00:21:37] ZFS when I increase the size because all
[00:21:40] of that is being taken care of by
[00:21:43] workflows that FSX runs in the
[00:21:46] background
[00:21:51] uh some customers are really ZFS Savvy
[00:21:54] users they like to use ZFS features
[00:21:58] um like snapshots and cloning some
[00:22:01] customers use this clone storage for as
[00:22:04] their test environments they take point
[00:22:07] in time snapshots
[00:22:09] and they tend to come to CFS because of
[00:22:13] those features
[00:22:17] AWS claims that we are the we are the
[00:22:20] top most customer obsessed company on
[00:22:23] planet Earth so no
[00:22:26] presentation from AWS is complete if I
[00:22:28] don't share a few customer stories one
[00:22:32] of our customers is Vela games there are
[00:22:35] game studio and they increased their
[00:22:40] build Time by 60 by using openfs open
[00:22:45] opencfs
[00:22:47] um The Challenge was they
[00:22:50] were using build graph which was
[00:22:55] um which was generating multiple which
[00:22:57] automated their build tasks
[00:23:00] um but they did uh using opencfs is uh
[00:23:04] they started saving uh or other
[00:23:07] checkpointing the output of intermediate
[00:23:10] build tasks and passing those output
[00:23:14] persisting those output and passing that
[00:23:16] to the next stage of the automated build
[00:23:19] task so that they do not have to build
[00:23:22] from scratch every time those next steps
[00:23:25] are running and they used cloning to do
[00:23:28] to achieve that which was like very fast
[00:23:31] and easy way to to clone uh to get a
[00:23:34] copy of the last output of the last
[00:23:37] stages
[00:23:40] uh rev.com is another customer and where
[00:23:44] they're looking for a fully managed high
[00:23:47] performance file system and they wanted
[00:23:49] to reduce the operational complexity and
[00:23:53] um they accelerated their ml training
[00:23:55] workflows uh workloads with no latency
[00:23:59] storage they reduce their operating
[00:24:01] costs by nearly 30 percent and also as I
[00:24:04] mentioned we publish some metrics uh to
[00:24:08] AWS Cloud watch using which they have
[00:24:11] visibility and they can monitor their
[00:24:14] file system performance
[00:24:17] uh to recap of what we have I have
[00:24:21] covered so far is
[00:24:24] um
[00:24:24] customers use FSX for opencfs because of
[00:24:28] the high performance storage
[00:24:30] um for latency sensitive and iops
[00:24:32] intensive use cases they use it because
[00:24:36] of Advanced ZFS capabilities which have
[00:24:40] been made simple and easy and it's a
[00:24:43] cost effective fully managed drop-in
[00:24:45] replacement for self-managed NFS
[00:24:50] going forward
[00:24:52] um this is the first time AWS is
[00:24:56] attending open CFS deaf Summit and we'd
[00:24:59] like to continue our engagement with the
[00:25:02] community
[00:25:04] um uh so far we run uh AWS we run
[00:25:09] opencfs on arm graviton architecture arm
[00:25:12] architecture so
[00:25:15] um whatever bugs we see we like to
[00:25:18] report back to the community whatever
[00:25:20] way we can fix them we'd like to
[00:25:22] Upstream those changes so we can fix
[00:25:24] them it's been only a year we have been
[00:25:26] operating up in CFS although we have
[00:25:29] another
[00:25:30] um so basically what I mean to say is
[00:25:35] um we'd like to grow on our learning and
[00:25:39] we'd like to learn from you all also and
[00:25:42] be more engaged with the community
[00:25:46] um
[00:25:47] we'd like to see more testing on arm
[00:25:49] architecture and if we can
[00:25:52] contribute in any way
[00:25:54] we'd like to do that
[00:25:56] and that's pretty much I have to say
[00:25:59] about FSX open CMS any questions so far
[00:26:04] [Applause]
[00:26:10] yeah go ahead
[00:26:19] you have to get
[00:26:20] a meditators
[00:26:23] no I so the question was have we looked
[00:26:26] at the ebbf project
[00:26:31] s
[00:26:35] and it actually has something to
[00:26:39] metadata information got it
[00:26:48] got it so the comment was have we looked
[00:26:50] into which is new so I'm not I advisor
[00:26:53] if I'm not
[00:26:55] basically okay so no we haven't so we
[00:26:58] looked into NFS stat which didn't give
[00:27:02] us what we wanted so right now that's
[00:27:04] why we do not have a clear path of
[00:27:07] sourcing the metadata statistics
[00:27:23] got it yeah I'll I can talk to you uh
[00:27:26] later after the conference and then can
[00:27:28] get to know more about it
[00:27:30] yes sir
[00:27:47] so the question was there's a slide on
[00:27:49] how do we we have tuned some of the ZFS
[00:27:52] tunings configurations uh to get
[00:27:54] performance and the question was did we
[00:27:57] do those as live tunings and what kind
[00:28:00] of tunings uh we gave so without going
[00:28:02] too much into implementation details uh
[00:28:05] first we monitor using Arc stats and
[00:28:08] other tools uh like uh the health of the
[00:28:11] file server uh how the how the file
[00:28:14] server is performing the iops and all
[00:28:17] that and we first try to tune the file
[00:28:21] systems in our development environment
[00:28:24] and try to drive the workload we do not
[00:28:26] we cannot do those tunings in on in
[00:28:30] production customer file system so first
[00:28:33] we try those out in our test environment
[00:28:35] and we conduct experiments uh we have a
[00:28:40] I have Patrick my colleague who recently
[00:28:42] did some tunings the tunings that I
[00:28:45] mentioned Arc you can certainly up to
[00:28:47] him and he can explain to you what all
[00:28:51] we did so basically our main goal is an
[00:28:56] optimal balance between performance and
[00:28:58] stability and and that is sort of our
[00:29:02] guiding tenet in deciding what kind of
[00:29:03] tunings we use
[00:29:06] do you have time to take more questions
[00:29:08] okay
[00:29:16] um so that's a good question and I'm
[00:29:18] oh sorry uh the the question is what
[00:29:21] encryption strategy do we use and I said
[00:29:24] that's a good question because it's not
[00:29:25] on top of my head but I can get back to
[00:29:27] you on that we have public documentation
[00:29:29] available for that
[00:29:39] the question is is encryption at rest
[00:29:43] is used is is it using ZFS encryption or
[00:29:48] something uh below the layer it's not
[00:29:51] using CFS encryption we use AWS
[00:29:55] encryption strategy which is below the
[00:29:57] layer below which sits below ZFS for
[00:30:00] encrypting them
[00:30:03] um you talk about backup and you said
[00:30:06] that he was using internal AWS
[00:30:07] technology to keep the dynamic system I
[00:30:09] was curious if you considered using zfs7
[00:30:15] so the question is uh we I mentioned
[00:30:18] that we do we use uh AWS infrastructure
[00:30:21] for backing up the file system and the
[00:30:24] question is have we considered using ZFS
[00:30:26] snapshots for backup uh yes we did
[00:30:29] consider uh ZFS snapshot but we decided
[00:30:33] uh to go with our infrastructure AWS
[00:30:35] internal infrastructure because that
[00:30:36] gives us uniformity over across multiple
[00:30:39] engines and also it gave us the way we
[00:30:43] wanted to design the feature for our
[00:30:45] customer
[00:30:53] foreign
[00:31:09] so the question is what kind of internal
[00:31:13] infrastructure that we use
[00:31:15] we AWS doesn't
[00:31:18] disclose that information because we
[00:31:20] keep it as an obstruction layer because
[00:31:23] so that customers we feel that
[00:31:26] information doesn't help customers in
[00:31:28] any way what customers care about and
[00:31:31] access to their file system over NFS
[00:31:33] since we offer opencfs and and how they
[00:31:38] are going to access from what kind of
[00:31:39] clients they are going to access so
[00:31:42] that's why you do not disclose that
[00:31:44] information
[00:31:45] physical therapy is the next corner is
[00:31:49] can you say again
[00:31:53] uh the NFS the question is if I have
[00:31:57] gotten your question is the NFS does NFS
[00:32:00] runs in kernel or in user space is that
[00:32:02] the question we run NFS on kernel in
[00:32:04] kernel
[00:32:10] because
[00:32:12] Amazon
[00:32:14] AWS right now the question is how much
[00:32:17] data is stored in AWS Amazon for opencfs
[00:32:22] um unfortunately I'm not the best person
[00:32:23] to answer that question
[00:32:25] um because we do not publish those data
[00:32:28] openly
[00:32:42] just
[00:32:48] so the question is uh have we considered
[00:32:50] looking into using L2 Arc or slog
[00:32:53] devices or do we just simply use Zippos
[00:32:57] uh we we did and our guiding tenet there
[00:33:04] is something that is simple to use for
[00:33:06] the customer and which gives best
[00:33:08] performance we are still looking into
[00:33:10] because DFS is so feature Rich we are
[00:33:13] still looking into multiple features
[00:33:15] which we can use so that we can drive
[00:33:17] even better performance for the
[00:33:19] customers but so far we do not offer ill
[00:33:23] to our device
[00:33:27] any other question
[00:33:32] going once going twice yes sir
[00:33:36] AWS
[00:33:47] um
[00:33:48] again that is something I am not the
[00:33:51] best person to answer but we launched in
[00:33:56] 2021 December last year so AWS has a
[00:33:59] conference called reinvent some of you
[00:34:02] may know it's a it's a largest
[00:34:04] conference for the community and we uh
[00:34:07] we uh declare we announced the ga
[00:34:11] General availability of FSX probe and
[00:34:13] CFS in that conference
[00:34:16] yes sir
[00:34:30] got it so the question is I mentioned uh
[00:34:33] a single FSX file system can have
[00:34:36] multiple uh FSX volumes so what is the
[00:34:39] what is it file system and how like how
[00:34:42] customers use the volumes so uh
[00:34:45] customers can use access those volumes
[00:34:48] using NFS export and they can create
[00:34:51] multiple FSX volumes uh multiple
[00:34:54] children FSX volumes to the root volume
[00:34:57] uh and they can all change since we
[00:35:00] allow the customers to change the NFS
[00:35:02] exports they can
[00:35:04] access those different children volumes
[00:35:07] using NFS exports
[00:35:13] sorry
[00:35:18] it's it's FSX volume is is something
[00:35:21] that we expose to the customer so uh
[00:35:23] it's it's visible by the customers using
[00:35:25] NFS
[00:35:27] yes sir
[00:35:32] uh the question is have we tried access
[00:35:35] volumes over is because you know we
[00:35:36] haven't
[00:35:42] yes sir
[00:35:43] okay can we take
[00:35:46] one more okay one last question
[00:35:55] yes we currently we offer uh NFS
[00:35:59] protocol so
[00:36:01] um
[00:36:03] Windows is uh any Windows client has to
[00:36:05] access over NFS
[00:36:08] I think that was
[00:36:10] the last question
[00:36:12] um thank you I hope I could
[00:36:19] so we'll break until 10 20 and then
[00:36:23] we'll come back for the next top
[00:36:25] if you have any questions uh please feel
[00:36:27] free to reach out to me we
[00:36:30] uh
[00:36:31] stand up say hi uh he works
[00:36:36] we have shooting
[00:36:38] we have mash
[00:36:40] and we have
[00:36:42] uh for AWS attending this conference
[00:36:45] thank you
[00:36:48] foreign
