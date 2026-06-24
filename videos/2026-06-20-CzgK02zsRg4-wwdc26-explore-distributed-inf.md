---
video_id: CzgK02zsRg4
title: "WWDC26: Explore distributed inference and training with MLX | Apple"
channel: Apple Developer
url: "https://www.youtube.com/watch?v=CzgK02zsRg4"
watched_date: 2026-06-20
watched_at: "2026-06-20T12:00:00Z"
watch_count: 1
duration_seconds: 1326
source: youtube-history-browser
added_date: 
history_label: Saturday
history_order: 55
watched_at_precision: date-from-history-label
watched_percent: 10
estimated_watched_seconds: 133
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Tatiana from Apple's MLX team demonstrated how to build a distributed computing cluster using multiple Macs connected via Thunderbolt 5 cables. The presentation covered the full stack: RDMA (Remote Direct Memory Access) over Thunderbolt for fast data transfer, JACCL (Apple's collective communication library) for coordinating across machines, and MLX (Apple's machine learning framework) for orchestrating distributed jobs. She showed two topology options—mesh (lowest latency, every machine connects directly to others) and ring (fewer cables, more bandwidth per link)—and explained how to enable RDMA, generate cluster configuration files, and launch distributed workloads. The talk demonstrated running models like Qwen 3.6 (27 billion parameters) and Kimi 2.6 (1 trillion parameters) across 4 M3 Ultras, achieving 3x speedup for inference and fine-tuning through tensor parallelism and data parallelism respectively.

To use this yourself: connect multiple Macs with Thunderbolt 5 cables, enable RDMA in each machine's settings, then use the `mlx.distributed_config` helper to generate a cluster configuration file. You can immediately start running distributed inference or fine-tuning by wrapping any existing single-device MLX command with `mlx.launch --hostfile <config>` from a connected machine. This lets you run massive language models that don't fit on a single Mac, achieve 3x+ speedup on inference and training, and keep all data private on your hardware using Python, Swift, C++, or command-line interfaces.

## Transcript

[00:00:07] Hi, I'm Tatiana, research scientist at MLX team.
[00:00:11] It's been a remarkable time for local LLMs:
[00:00:14] models keep getting larger
[00:00:16] and gaining new amazing capabilities --
[00:00:18] becoming smarter and handling harder problems.
[00:00:22] And as they improve, we use them for more: longer contexts, harder tasks,
[00:00:26] more complex workflows.
[00:00:28] Eventually, memory, compute, or bandwidth on a single machine becomes a limitation.
[00:00:35] In our WWDC 26 video "Run local agentic AI on the Mac using MLX"
[00:00:39] it is shown how to run AI agents locally.
[00:00:42] But when you have multiple devices, you can take local AI even further,
[00:00:47] running larger LLMs or accelerating them
[00:00:50] through distributed inference and training.
[00:00:53] Today, we'll take a deep dive into scaling across multiple Macs with MLX,
[00:00:59] using the hardware right on your desk.
[00:01:02] We'll start with the command line interface to get models running
[00:01:05] on your machines,
[00:01:07] move to the Python API for experimentation,
[00:01:10] and finish with Swift for embedding these workflows directly into your apps.
[00:01:15] Let's start!
[00:01:17] First, we'll look at the full hardware and software stacks
[00:01:20] to make distributed workloads on Apple Silicon possible.
[00:01:24] Then we'll put everything together: turn four M3 Ultras into a cluster.
[00:01:29] We'll walk through every step: choosing the right topology to connect machines,
[00:01:34] enabling fast communication, and launching distributed jobs.
[00:01:38] Once the cluster is ready, we'll get to the exciting part:
[00:01:42] fast and local distributed LLM inference and finetuning.
[00:01:46] We'll run it with MLX, compare it side by side against a single Mac,
[00:01:51] and look at how MLX distributes the model across the cluster.
[00:01:56] Having most examples in command line interface,
[00:02:00] in the end we'll show how distributed communication
[00:02:03] is also exposed to you via Python, Swift and C++ APIs.
[00:02:09] Let's start by looking at distributed communication for Apple Silicon.
[00:02:14] To send and receive data fast,
[00:02:16] machines need to be connected with a physical link
[00:02:19] — an interconnect.
[00:02:21] On top of that, we also need a transport protocol —
[00:02:24] a mechanism that pushes bytes
[00:02:26] from one machine's memory to another's.
[00:02:29] Starting in macOS 26.2,
[00:02:32] Remote Direct Memory Access protocol, shortly RDMA,
[00:02:36] is supported over Thunderbolt 5.
[00:02:38] RDMA moves data directly from one machine's memory to another's,
[00:02:43] avoiding most CPU and operating system overhead.
[00:02:47] RDMA over Thunderbolt gives us the high-bandwidth —
[00:02:50] low-latency communication
[00:02:52] we need for distributed workloads.
[00:02:54] However, alone, it gives us raw data movement between two machines only.
[00:02:59] Thus, distributed programs need something higher-level —
[00:03:03] a communication backend
[00:03:05] which provides communication primitives for sending data
[00:03:08] between individual machines
[00:03:10] or coordinating across the entire group.
[00:03:13] These two operations are building blocks of distributed training and inference.
[00:03:17] And this is where JACCL comes in.
[00:03:21] JACCL is an open-source collective communication library
[00:03:24] built by Apple.
[00:03:26] It leverages RDMA over Thunderbolt
[00:03:28] and gives you collective communication primitives
[00:03:31] for sending data between machines
[00:03:33] and combining results across the group —
[00:03:35] without managing any of the low-level transport yourself.
[00:03:39] And it's not limited to machine learning — any distributed workload on Apple Silicon
[00:03:44] can be built on top of it.
[00:03:46] And the final piece of the stack is a machine learning framework
[00:03:50] that uses the communication backend for distributed inference and training —
[00:03:55] that's MLX.
[00:03:57] MLX is an open-source machine learning library
[00:04:00] built by Apple for Apple Silicon.
[00:04:02] It leverages JACCL for low-latency distributed communication
[00:04:06] and provides tools for orchestrating distributed jobs across the cluster.
[00:04:11] If you're new to MLX, check out our video
[00:04:14] "Getting Started with MLX on Apple Silicon" from WWDC25.
[00:04:20] So now we understand the full stack.
[00:04:22] Let's put it all together and build a cluster —
[00:04:25] a group of machines that work together on the same task.
[00:04:29] We will use 4 M3 Ultras.
[00:04:32] To setup the cluster, we need to connect the machines with Thunderbolt 5 cables.
[00:04:37] There are different ways to wire them together,
[00:04:40] and the topology directly affects the communication time.
[00:04:44] So to begin with, we'll look at what defines that time.
[00:04:48] Next, we'll look at how to actually connect the machines —
[00:04:51] which topologies JACCL supports, and the trade-offs between them.
[00:04:56] After that, we'll show how to enable RDMA on the machines for fast communication.
[00:05:01] And finally, we'll launch distributed jobs on the cluster using MLX.
[00:05:08] So, communication time has two components:
[00:05:11] latency and transfer time.
[00:05:13] Latency is the fixed cost paid for each communication operation,
[00:05:17] independent of the amount of data being sent.
[00:05:22] Transfer time is the cost of moving the data though the link;
[00:05:26] it grows with message size
[00:05:28] and depends on the bandwidth of the link.
[00:05:32] For small messages, the data movement cost is tiny,
[00:05:35] so latency dominates.
[00:05:39] For large messages, the trade off is opposite.
[00:05:42] Depending on whether communication is latency-bound or bandwidth-bound,
[00:05:46] we may prefer different topologies.
[00:05:50] JACCL supports two of them: a mesh and a ring.
[00:05:54] In a full mesh, every machine connects directly to every other,
[00:05:58] thus any group communication has the lowest possible latency.
[00:06:02] In a ring, each node connects only to its two neighbors.
[00:06:07] Communication between nonadjacent nodes must travel through intermediate machines
[00:06:12] which increases latency.
[00:06:14] However, the ring requires fewer cables and ports per machine,
[00:06:18] making it easier to scale to more nodes.
[00:06:21] And because each node has only two connections,
[00:06:24] we can use the extra Thunderbolt ports
[00:06:26] to run two or tree cables per neighbor (depending on the Mac)
[00:06:30] — thus increasing the bandwidth per link
[00:06:31] and reducing transfer time.
[00:06:34] When machines are connected into a mesh,
[00:06:37] we have the flexibility to route each communication
[00:06:40] through either a mesh topology or a ring topology.
[00:06:46] What's nice about JACCL, it automatically picks the best topology
[00:06:50] depending on the message size and communication operation —
[00:06:54] mesh when latency matters,
[00:06:57] ring when bandwidth matters.
[00:06:59] For this flexibility, let's connect all M3 Ultras into a mesh.
[00:07:06] As we connected all M3 Ultras together,
[00:07:08] now we need to enable RDMA on all machines.
[00:07:11] Open settings on the machine, search for "RDMA",
[00:07:19] click on "Enable RDMA over Thunderbolt",
[00:07:24] enable RDMA, and reboot.
[00:07:28] Great!
[00:07:29] Macs are connected with Thunderbolt 5 cables,
[00:07:32] and RDMA is enabled.
[00:07:33] Now we need a way to launch distributed programs.
[00:07:38] One way to do it, is over the local network,
[00:07:41] for example, through wifi or ethernet.
[00:07:44] From any machine with SSH access to the cluster,
[00:07:47] for example MacBook in my case,
[00:07:50] we connect to each Mac, start the program,
[00:07:53] and from that point on,
[00:07:54] all machines communicate directly over the Thunderbolt links.
[00:07:59] MLX provides a launch helper, which exactly does all of this for you!
[00:08:05] You run mlx.launch on your MacBook and it orchestrates the cluster.
[00:08:11] You give it the executable you want to run
[00:08:14] and a JSON hostfile describing your cluster.
[00:08:17] From there, it SSHes into each node using hostnames from provided hostfile
[00:08:23] and starts the executable on every machine.
[00:08:26] Let's see how the hostfile that describes the cluster should look like.
[00:08:31] It is a JSON array — one entry per node.
[00:08:35] "ssh" is the hostname used by mlx.launch to reach the machine.
[00:08:40] "ips" is the machine's IP on your local network
[00:08:43] used by JACCL for initial coordination between nodes.
[00:08:47] And "rdma" is a list of the RDMA device names
[00:08:51] for each Thunderbolt peer connection.
[00:08:54] You can write it manually, but MLX also provides
[00:08:56] a helper script `mlx.distributed_config` that generates it for you.
[00:09:02] You pass the list of hostnames, and an output path.
[00:09:06] You can also embed environment variables in the config.
[00:09:10] They will be set automatically on every node at launch time.
[00:09:14] Here we set MLX_METAL_FAST_SYNCH=1,
[00:09:18] which enables faster GPU-to-CPU synchronization.
[00:09:22] It is critical for distributed tasks because computation runs
[00:09:26] on the GPU
[00:09:27] while communication runs on the CPU.
[00:09:30] You can also pass the --auto-setup flag
[00:09:32] to configure the Thunderbolt network automatically.
[00:09:36] Communication --backend argument defines whether it is a mesh or ring:
[00:09:41] for a mesh, --backend is set to jaccl, as in this example;
[00:09:45] for a ring, we would change it to jaccl-ring.
[00:09:49] Let's run this command and generate the hostfile for our cluster.
[00:09:54] First, it checks that all hosts are reachable over SSH.
[00:09:59] Then it probes each machine's Thunderbolt ports
[00:10:02] to discover which machines are physically connected to which
[00:10:06] — building a map of the topology.
[00:10:08] Since we passed --auto-setup, it disables the Thunderbolt Bridge
[00:10:12] on all machines
[00:10:13] and configures each Thunderbolt link for RDMA.
[00:10:17] Finally, it writes a JSON hostfile with everything mlx.launch needs.
[00:10:22] Note, that without --auto-setup flag, script prints the configuration commands,
[00:10:27] so you can review them and run yourself.
[00:10:31] Now, the cluster is ready.
[00:10:33] Let's move to the exciting part — distributed language model inference
[00:10:37] and finetuning.
[00:10:39] And the easiest way to start is via command line interface
[00:10:43] and MLX LM.
[00:10:45] MLX LM is an open-source Python package
[00:10:48] built on top of MLX
[00:10:49] that provides command-line tools
[00:10:52] and a Python API for running language models locally
[00:10:55] on Apple Silicon.
[00:10:56] Check out our video, "Explore large language models on Apple Silicon with MLX"
[00:11:02] from WWDC25 to get started on a single device.
[00:11:07] As we showed last year, chatting with a model on a single Mac
[00:11:11] can be done via command line interface with mlx_lm.chat.
[00:11:16] We run it in the terminal, specifying the model we want to use,
[00:11:19] for example, Qwen 3.6,
[00:11:22] and the maximum number of tokens for the response.
[00:11:25] Under the hood, MLX LM loads and runs the model on a single machine.
[00:11:31] To chat with the same model on the cluster via command line interface,
[00:11:36] we wrap the command with mlx.launch.
[00:11:39] On our MacBook, in the terminal we run mlx.launch
[00:11:43] with the --hostfile pointing to our cluster configuration.
[00:11:47] After the double dash, we pass the exact same mlx_lm.chat command —
[00:11:51] but using the remote path to the executable on each node.
[00:11:56] The command is almost identical,
[00:11:58] MLX LM shards the model and coordinates the distributed inference for you.
[00:12:03] Keep in mind that all necessary libraries like MLX must be installed on each Mac
[00:12:09] and the executable must be accessible on all machines.
[00:12:14] One line via command line interface, and we're running a model
[00:12:18] spread across the entire cluster!
[00:12:21] Let's try both side by side and chat with Qwen 3.6 —
[00:12:25] a 27-billion-parameter model —
[00:12:27] on a single M3 Ultra and on 4 of them.
[00:12:32] I've already started mlx_lm.chat on both sides —
[00:12:35] on the left, the model is loaded on a single M3 Ultra;
[00:12:39] on the right, it's sharded across four machines.
[00:12:43] Let's prompt both with "Implement a transformer model in MLX."
[00:12:50] It is a quite impressive speed up!
[00:12:52] The cluster generates tokens at nearly three times the rate
[00:12:55] of a single machine
[00:12:57] for Qwen 3.6 model.
[00:12:59] As we see, running a model across multiple Macs
[00:13:03] can significantly boost inference speed.
[00:13:06] The exact speedup depends on the model size and architecture.
[00:13:10] But time improvement is not the only reason to go distributed,
[00:13:14] sometimes a model is simply too large for one machine.
[00:13:18] Kimi 2.6, for example, has 1 trillion total parameters.
[00:13:23] Even with 8-bit quantization,
[00:13:26] the weights alone require about one terabyte of memory.
[00:13:30] That does not fit on a single M3 Ultra, but it can fit across four.
[00:13:35] So how do we actually split the weights and computation across machines?
[00:13:40] MLX and MLX LM support two approaches: pipeline and tensor parallelism.
[00:13:47] Pipeline parallelism splits the model by depth.
[00:13:50] In this case, each machine holds a group of layers,
[00:13:53] and data moves through the machines sequentially.
[00:13:56] It does not speed up the inference, because each token still has to pass
[00:14:01] through the layer groups one after another.
[00:14:04] But the benefit is simple communication: machines only exchange activations
[00:14:09] at the boundaries between layer groups.
[00:14:13] Tensor parallelism splits the model by width.
[00:14:15] In this case, each machine holds part of every layer,
[00:14:19] so all machines process the same token at the same time.
[00:14:24] It improves inference speed due to parallelized per-layer computation.
[00:14:28] However the trade-off is much more frequent communication,
[00:14:32] that happens at every layer and for every token.
[00:14:36] This makes low latency important,
[00:14:38] and that is why the mesh topology is crucial for this case —
[00:14:42] every machine can reach every other machine in a single hop.
[00:14:48] Tensor paralelism is the default sharding strategy in MLX LM.
[00:14:52] To shard the model with pipeline parallelism,
[00:14:54] we can simply append a flag --pipeline to the command.
[00:14:58] Note, that not all models support pipeline parallelism.
[00:15:03] Now, let's chat with a one-trillion-parameter Kimi 2.6
[00:15:07] on our cluster.
[00:15:09] For this we use mlx.launch from our MacBook as before,
[00:15:14] pointing to the hostfile.
[00:15:16] I'm not passing the --pipeline flag, so we're using tensor parallelism.
[00:15:20] We need to wait a moment — mlx.launch is connecting to every machine,
[00:15:24] MLX LM loads and shards the model,
[00:15:27] and starts the chat.
[00:15:29] Great, the model is loaded!
[00:15:31] Let's prompt model with:
[00:15:33] "Implement machine learning architecture for GPT in Python with MLX".
[00:15:42] And there we go — with one command, a massive trillion-parameter model
[00:15:46] is running locally across your Macs, answering your questions.
[00:15:54] With MLX and MLX LM, you can not only run language model inference,
[00:15:58] you can also fine-tune models on your hardware.
[00:16:01] Fast, efficient, and fully private — your data never leaves your machines.
[00:16:07] Let's start with a single Mac, and then scale to our cluster.
[00:16:11] When fine-tuning or training on a single machine,
[00:16:14] we split the training data into batches —
[00:16:17] a set of multiple examples.
[00:16:20] For each batch, the Mac computes gradients
[00:16:24] and updates the model weights.
[00:16:26] We repeat this process for one or more passes over the training dataset,
[00:16:30] until the model reaches the desired quality.
[00:16:33] The faster we process the training data,
[00:16:35] the sooner fine-tuning finishes.
[00:16:37] So how can we use multiple machines to speed this up?
[00:16:41] The idea is straightforward.
[00:16:43] We replicate the model on every Mac.
[00:16:46] Each machine receives a different batch of data and computes gradients locally.
[00:16:51] Then we average the gradients, so the model's update uses information
[00:16:56] from all batches.
[00:16:57] This is called data-parallel training because the model is replicated,
[00:17:01] while the data is processed in parallel across machines —
[00:17:05] this is what gives us the speedup.
[00:17:07] So with N machines we can process data up to N times faster.
[00:17:12] Sounds amazing!
[00:17:13] Lets see how we can use data parallelism with MLX LM.
[00:17:18] As before, the only difference from a single device
[00:17:21] is launching the job with mlx.launch
[00:17:23] from your MacBook,
[00:17:24] specifying a path to mlx_lm.lora on remote machines.
[00:17:29] Data sharding is handled by MLX LM and the command is almost identical —
[00:17:34] we scale --batch-size by the number of devices
[00:17:37] so each machine still processes
[00:17:39] the same number of samples per step as before.
[00:17:43] Let's fine-tune Qwen 3.5 with 9 billion parameters
[00:17:47] on a single machine and on the cluster,
[00:17:50] and compare the number of tokens the model processes per second.
[00:17:55] We are launching fine-tuning on a single device on the left
[00:17:58] and on the cluster on the right
[00:18:00] using mlx.launch and hostfile,
[00:18:03] specifying path to mlx_lm.lora on the remote machine.
[00:18:07] First, it loads data and model; and then training starts.
[00:18:10] Single M3 Ultra is processing around 180 tokens per second,
[00:18:16] while on the cluster we process around 600 tokens per second,
[00:18:21] which gives us more than 3 times speed up for fine-tuning.
[00:18:25] Now, with MLX, you can turn your devices into a local training cluster
[00:18:30] for efficient fine-tuning without moving to a cloud.
[00:18:34] So far, we used command line interface for distributed inference
[00:18:38] and fine-tuning within MLX LM.
[00:18:41] However, MLX provides a fine-grained control
[00:18:44] over sharding and distributed operations,
[00:18:47] via flexible Python, Swift, and C++ APIs.
[00:18:51] This allows you to experiment with models in Python and C++
[00:18:55] or embed models into your App with Swift.
[00:18:58] Let's look at the examples.
[00:19:01] To run distributed inference with Python API and MLX LM,
[00:19:05] we first initialize the distributed group for communication.
[00:19:08] Then, define the type of parallelism we want,
[00:19:12] for example, tensor parallelism.
[00:19:14] Finally, we shard the model using the sharded_load function.
[00:19:18] After that, we use the model exactly as we would on a single device —
[00:19:23] MLX LM handles all distributed communications under the hood.
[00:19:28] To have more control over the model and its sharding,
[00:19:31] we can use low-level primitives from MLX itself.
[00:19:35] For example, after defining a simple Linear layer,
[00:19:38] we can shard it with tensor parallelism using shard_linear function.
[00:19:43] You can even control basic distributed operations like all reduce.
[00:19:48] In Python, Swift or C++ after initializing the distributed group via JACCL,
[00:19:53] we perform a collective distributed sum across all Macs for our tensor
[00:19:58] using corresponding MLX primitives.
[00:20:01] As we pointed out at the beginning of the session,
[00:20:04] JACCL is available on its own
[00:20:06] and you can leverage it for any applications
[00:20:09] requiring distributed communication,
[00:20:12] even non-ML applications.
[00:20:14] JACCL can be built without MLX and it provides a C++ API
[00:20:19] with communication primitives:
[00:20:21] after initializing a JACCL group,
[00:20:23] we again perform a collective distributed sum across all Macs
[00:20:27] for our tensor but via JACCL directly, not MLX.
[00:20:33] Now you know both high-level and low-level APIs,
[00:20:36] for distributed inference and training with MLX and JACCL,
[00:20:39] and you are ready to build advanced distributed workflows with MLX.
[00:20:45] Throughout this session, we looked at the full stack
[00:20:47] that makes distributed training and inference
[00:20:50] possible on Apple Silicon —
[00:20:52] from RDMA over Thunderbolt,
[00:20:55] all the way up to MLX and MLX LM.
[00:20:58] We showed you how easy it is to scale from a single device to multiple devices,
[00:21:03] and the benefits it brings:
[00:21:05] faster inference, the ability to run trillion-parameter models,
[00:21:09] and faster fine-tuning;
[00:21:11] all with minimal changes to your single device code,
[00:21:14] supporting command line interface, Python, Swift and C++ APIs.
[00:21:20] With distributed cluster, now you can run local AI agents powered entirely by MLX —
[00:21:26] fast, private, and on the hardware you own.
[00:21:31] To know more, check out our WWDC 2026 video
[00:21:34] "Run local agentic AI on the Mac using MLX".
[00:21:38] To further dive into advanced distributed features —
[00:21:42] including custom parallelism strategies and training loops,
[00:21:45] check out our documentation.
[00:21:47] You can also use MLX LM to serve models distributedly with the built-in server.
[00:21:54] We can't wait to see what you build with MLX on Apple Silicon!
