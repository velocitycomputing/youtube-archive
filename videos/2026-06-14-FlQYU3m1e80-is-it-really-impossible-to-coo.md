---
video_id: FlQYU3m1e80
title: Is It Really Impossible To Cool A Datacenter In Space?
channel: Scott Manley
url: "https://www.youtube.com/watch?v=FlQYU3m1e80"
watched_date: 2026-06-14
watched_at: "2026-06-14T12:00:00Z"
watch_count: 1
duration_seconds: 1470
source: youtube-history-browser
added_date: 
history_label: Sunday
history_order: 70
watched_at_precision: date-from-history-label
watched_percent: 75
estimated_watched_seconds: 1102
summary_model: claude-haiku-4-5
tagging_model: claude-haiku-4-5
proposed_tags: []
proposed_entities: []
status: new
routed_to: null
---

## Summary

Scott Manley demonstrates that cooling datacenters in space is technically feasible using Stefan-Boltzmann radiation physics. A 20 kW datacenter on a Starlink V3 satellite needs approximately 23 square meters of radiators operating at 80°C—well within the satellite's ~24.5 square meter bus. The analysis accounts for external heat sources (solar illumination, Earth's reflected sunlight, and thermal radiation), showing a best-case 10° attitude tolerance and a worst-case scenario requiring modest deployable radiators. Scaling to 100 kW per rack requires larger radiators (~20 m² extra per 20 kW), but remains achievable with proper orientation and reflective shielding. The key bottleneck shifts from radiation area to heat transport: moving 100 kW requires ~70 liters of coolant per minute, necessitating careful pump design and fluid selection (ammonia or two-phase systems outperform water in space).

For anyone designing space-based infrastructure, the actionable insight is that hardware operating temperature is the critical lever—chips designed to tolerate 97°C instead of 65°C dramatically reduce radiator requirements and make the economics viable. Practical implementation requires custom silicon, attitude control systems to orient radiators away from the Sun, efficient thermal plumbing, and distributed satellite architectures to minimize inter-node latency rather than attempting single massive orbital datacenters.

## Transcript

[00:00:04] Hello, it's Scott Manley here. People
[00:00:07] tell me that cooling data centers in
[00:00:10] space is easy because space is cold.
[00:00:13] Other people say it's nigh on impossible
[00:00:15] because on Earth we have conduction and
[00:00:17] convection to get rid of the heat, but
[00:00:19] in the vacuum of space all you have is
[00:00:21] radiation. Now, this is one of those
[00:00:23] things that people seem to be arguing
[00:00:25] over repeatedly and I kind of wanted to
[00:00:29] just sit down and give you a rough idea
[00:00:31] of how you actually do the math so that
[00:00:33] we can know the real answer.
[00:00:36] There are all sorts of software packages
[00:00:38] out there that are designed for
[00:00:39] professionals or you know, people that
[00:00:41] are actually designing spacecraft will
[00:00:43] have software to do all this. They model
[00:00:45] the heat flow, the absorption,
[00:00:47] you know, the emission and they are all
[00:00:49] very expensive pieces of software that
[00:00:51] are very accurate, but we're not going
[00:00:52] to do this because this adds a lot of
[00:00:55] complexity that actually gets in the way
[00:00:56] of understanding the basic numbers.
[00:00:58] Instead, I'm kind of going to aim to do
[00:01:00] this with like pen and paper. Actually,
[00:01:03] that's a really bad idea here because my
[00:01:04] handwriting's terrible. So, I'll
[00:01:06] probably just like put equations on the
[00:01:09] screen and print the numbers up there,
[00:01:10] but either way you should be able to
[00:01:12] follow along.
[00:01:13] So, to figure out the temperature of an
[00:01:15] object in space, you figure out how much
[00:01:18] energy is coming in, how much is being
[00:01:20] absorbed and then given the surface area
[00:01:22] of the radiators, you then figure out
[00:01:24] how much heat those will emit at a given
[00:01:26] temperature and you basically need to
[00:01:27] balance the incoming energy with the
[00:01:29] outgoing energy to get the temperature.
[00:01:32] Now, in real spacecraft, the geometry of
[00:01:34] all this is really important, but to get
[00:01:36] started, we're going to work with a very
[00:01:38] simplified model of a spacecraft.
[00:01:41] So, let's start with the easiest example
[00:01:43] I can imagine. Imagine you have a
[00:01:44] spacecraft that has a bunch of graphics
[00:01:47] cards on it, right? GPUs all over one
[00:01:50] side. Now, it doesn't really matter what
[00:01:51] the exact hardware that's on there
[00:01:53] because after all, by the time you watch
[00:01:55] this, it could well be out of date.
[00:01:58] Let's take a popular estimate of about
[00:02:00] 20 kW of power on a Starlink V3
[00:02:04] satellite. So, the spacecraft will be
[00:02:07] consuming 20 kW of electricity, and it
[00:02:10] will be taking that in from the solar
[00:02:12] panels and converting that into heat.
[00:02:14] And cat memes.
[00:02:16] In the case of Starlink, a decent chunk
[00:02:18] of that energy is also coming out as
[00:02:20] radio waves, but if it's just a computer
[00:02:23] that is crunching numbers, all of that
[00:02:25] power ends up being converted into heat.
[00:02:26] So,
[00:02:27] now we specified how much heat is coming
[00:02:29] in, that's 20 kW. Let's figure out the
[00:02:32] radiator sizes that are needed from
[00:02:34] first principles.
[00:02:36] Now, for those of you that haven't done
[00:02:37] physics, the amount of heat that is
[00:02:39] emitted by a surface is covered by the
[00:02:42] Stefan-Boltzmann law, which is stupidly
[00:02:44] simple. It says the amount of energy
[00:02:46] emitted is proportional to the
[00:02:48] temperature raised to the fourth power,
[00:02:50] multiplied by the Stefan-Boltzmann
[00:02:52] constant, right? And this is physics, so
[00:02:54] temperatures, of course, measured
[00:02:56] relative to absolute zero, in Kelvin, or
[00:02:59] in Rankine, if you're weird. Uh so, room
[00:03:01] temperature of 20 C or 68 F, that's
[00:03:05] about 293 K,
[00:03:07] and plugging that in with 1 square meter
[00:03:10] of surface, it tells you that it emits
[00:03:12] about 420 W.
[00:03:15] Blazing, right? Now, increasing the
[00:03:17] temperature very quickly increases the
[00:03:19] power radiated. Doubling the temperature
[00:03:21] increases the radiated thermal energy by
[00:03:24] a factor of 16, right? Double it, you
[00:03:27] get a factor of 16 increase, that's
[00:03:29] huge. There's another factor we need to
[00:03:31] include, and that's the emissivity of
[00:03:33] the surface, right? How much it emits.
[00:03:35] And this is a simple num- number between
[00:03:37] either zero and one, which uh it defines
[00:03:40] how good the surface is at emitting
[00:03:42] blackbody radiation. I mean, rough,
[00:03:45] black surfaces tend to have high
[00:03:47] emissivities, while really perfectly
[00:03:49] smooth, shiny surfaces are bad at
[00:03:51] emitting heat and actually have low
[00:03:53] emissivities.
[00:03:54] Also, the number if frequently changes
[00:03:57] with wavelength. So, things tend to be
[00:03:59] better emitting heat in the infrared and
[00:04:00] not so good in the, you know, visible or
[00:04:02] vice versa. I'm largely going to ignore
[00:04:05] this initially and will add it in later,
[00:04:07] but you sort of need to know that this
[00:04:09] exists and I also need to make sure all
[00:04:10] the physicists out there aren't typing
[00:04:12] in comments telling me I forgot it.
[00:04:15] So, now
[00:04:16] imagine our Starlink satellite trying to
[00:04:18] get rid of 20 kilowatts at room
[00:04:21] temperature. At 420 watts per square
[00:04:23] meter,
[00:04:24] it would need about 50 square meters.
[00:04:26] Now, we can divide that by two because a
[00:04:28] thin flat spacecraft like Starlink has
[00:04:32] two sides. 25 square meters for the
[00:04:34] entire satellite. So, what is the
[00:04:36] surface area of the core of the Starlink
[00:04:38] satellite? Well, we're looking at the V3
[00:04:41] satellites and the only ones that we've
[00:04:42] actually seen tested are the dummy
[00:04:44] satellites that are deployed from
[00:04:46] Starship tests. And those
[00:04:48] look to be about 7 meters wide on the
[00:04:50] rails with two per rack. So, let's just
[00:04:52] say it's 7 meters by 3 and 1/2 meters.
[00:04:54] That's 24.5 square meters per side. And
[00:04:58] wow, I did not expect this to be so
[00:05:00] close. Like, I literally just put those
[00:05:02] numbers in and this is what I ended up
[00:05:03] with, right? But, we have a lot of other
[00:05:05] things to account for, but
[00:05:07] ideal situation would be that we emit
[00:05:09] all the thermal radiation from the sat,
[00:05:11] a flat satellite bus without having to
[00:05:13] add any deployable radiators or anything
[00:05:15] around it.
[00:05:16] So, now
[00:05:18] let's bump up the temperature. Increase
[00:05:20] the emission and in turn, this lets us
[00:05:22] reduce the surface area that's required.
[00:05:25] So, now let's imagine that our radiators
[00:05:27] are operating at 80 Celsius, right? Or
[00:05:30] 353 Kelvin. And that is pretty hot for
[00:05:33] silicon chips, but it is still doable,
[00:05:35] right? Now, the radiated power at 80
[00:05:38] Celsius is 880 watts per square meter.
[00:05:41] That's more than twice what we got at
[00:05:42] room temperature. That's a huge
[00:05:43] advantage. And of course, our required
[00:05:45] radiators are now 23 square meters. We
[00:05:47] only need half the satellite to cool it.
[00:05:50] Uh and that of course also assumes that
[00:05:52] our emissivity is high, right? The
[00:05:54] emissivity is close to one.
[00:05:57] Now, obviously having higher temperature
[00:05:59] radiators really helps a lot, but we
[00:06:02] can't just keep raising the temperature
[00:06:04] because the first law of thermodynamics
[00:06:06] tells us that heat only flows from hot
[00:06:08] to cold. So, you have to imagine the
[00:06:10] coolant is flowing through the system
[00:06:12] past the servers and cooling them down,
[00:06:14] and then flows out to the radiator
[00:06:16] panels, right? And
[00:06:17] that means the fluid has to be colder
[00:06:19] than the operating temperatures of your
[00:06:21] chips. And similarly, uh if you look at
[00:06:24] the space station, the radiators that
[00:06:25] cool down the crew segment could be
[00:06:27] smaller if they were allowed to run
[00:06:29] hotter, but the crew have a limit on the
[00:06:31] cabin temperatures where they are
[00:06:33] comfortable, right?
[00:06:34] Granted, you can actually have a heat
[00:06:36] pump that raises the temperature of the
[00:06:38] radiators above what you the area you're
[00:06:39] cooling, but then you're expanding
[00:06:41] energy to do this. Regardless, my point
[00:06:43] is that the radiator areas need to cool
[00:06:46] 20 kW of GPUs is smaller than the bus of
[00:06:50] a V3 Starlink satellite. But, the
[00:06:53] problem isn't solved by any means. This
[00:06:55] is just a starting point to get everyone
[00:06:57] up to speed on the idea of thermal
[00:06:59] balance. The satellite does not exist in
[00:07:01] a vacuum. Well, actually it doesn't
[00:07:03] exist in a vacuum, but it doesn't exist
[00:07:04] in space without outside influences. So,
[00:07:07] we have to talk about the sun and the
[00:07:09] Earth. There is a classic problem in
[00:07:12] astrophysics that we learn where you
[00:07:13] derive the temperature of an object
[00:07:15] based upon its distance from the sun. An
[00:07:17] object like say an asteroid or a planet
[00:07:19] or a spacecraft. What you do is you
[00:07:22] figure out how much heat it absorbs from
[00:07:23] the sun, and then how hot it has to be
[00:07:26] to emit all that heat. So, we imagine
[00:07:29] our object as a flat panel facing square
[00:07:32] on to the sun at the distance of the
[00:07:34] Earth it gets hit by 1,356 W of thermal
[00:07:37] power per square meter. Now, not all of
[00:07:40] that gets absorbed. Some of it will be
[00:07:41] reflected and scattered. And so, there's
[00:07:43] a difference between a black rock and
[00:07:45] say a highly reflective mirror. The
[00:07:48] ability to absorb light is the thermal
[00:07:50] absorptivity, right? And so, it's the
[00:07:53] counterpart to emissivity that I
[00:07:55] mentioned earlier. In fact, it's
[00:07:56] literally the twin. Uh and for the same
[00:07:59] wavelength, it should actually take the
[00:08:01] same value. There's something called
[00:08:02] Kirchhoff's law of thermal radiation,
[00:08:04] which says that the emissivity and the
[00:08:07] absorptivity are the same at any
[00:08:09] wavelength. Right? And this is a pretty
[00:08:11] cool and important result. It actually
[00:08:14] causes stops a lot of problems in
[00:08:15] thermodynamics. But, I need to point out
[00:08:18] that very recently there's some people
[00:08:19] using some very clever tricks with
[00:08:21] metamaterials have demonstrated uh the
[00:08:24] ability to break the symmetry in very
[00:08:26] narrow wavelength ranges. And this is
[00:08:29] all very cool academic work, but it's
[00:08:31] not going to change the landscape
[00:08:32] overnight. So, we are going to assume
[00:08:34] for now that the emission and absorption
[00:08:37] use exactly the same factor.
[00:08:39] So, for a simple gray body with no
[00:08:41] variation in the emission or absorption
[00:08:43] with frequency, the absorptivity and the
[00:08:46] emissivity factors will actually cancel
[00:08:48] out for a body that is getting
[00:08:49] illuminated by the sun.
[00:08:51] And that means that our 1 square meter
[00:08:53] of surface exposed to 1,356
[00:08:56] W of power needs to emit the same amount
[00:08:59] back out. And it needs to do that and to
[00:09:02] do that it needs to be at a temperature
[00:09:04] of about 393 K
[00:09:06] or 120 C, which is above the boiling
[00:09:09] point of water. This is roughly the
[00:09:11] temperature of the surface of the moon
[00:09:13] at midday with the sun high in the sky.
[00:09:16] On the Earth, we don't see these
[00:09:18] temperatures being reached during the
[00:09:19] middle of the day because the surface
[00:09:21] transfers heat into the atmosphere, and
[00:09:23] that tends to keep the surface at a more
[00:09:25] reasonable temperature.
[00:09:27] How about a two-sided panel floating in
[00:09:29] space that has twice the surface area
[00:09:32] for emission? In that case, the
[00:09:34] equilibrium temperature drops to 330 K
[00:09:37] or 57° C because you've got twice the
[00:09:40] emitting area. And if you've got say a
[00:09:42] two-sided panel that's exposed to the
[00:09:44] sun, you can have different surface
[00:09:46] materials on each side. For example, you
[00:09:48] can have low absorption on the sunny
[00:09:49] side and high emission on the backside,
[00:09:52] and that'll lower the temperature even
[00:09:53] further still. This is a kind of like
[00:09:56] trick that you will see spacecraft
[00:09:57] designers using to balance the thermals
[00:10:00] on their spacecraft.
[00:10:02] Solar panels are of course an excellent
[00:10:04] example of a flat surface in space that
[00:10:07] has to be pointed at the sun. And they
[00:10:09] have the added bonus of converting some
[00:10:11] of the power they absorb from the sun
[00:10:13] into electricity and sending that power
[00:10:15] elsewhere. So, the operating temperature
[00:10:17] of solar panels on spacecraft drops a
[00:10:20] bit lower than an idealized flat plane.
[00:10:24] So, what about the panels that aren't
[00:10:26] directly face on to the sun? Well, how
[00:10:28] does that change, right? What really
[00:10:30] matters is the cross-section that these
[00:10:32] panels offer to the incoming light. And
[00:10:35] for a point source, this varies with the
[00:10:37] angle. So, as the angle turns edge on,
[00:10:40] the amount of the cross-section drops
[00:10:42] off. It's just like a sine wave that
[00:10:44] varies with the angle. So, with the sun
[00:10:46] at 90°, you get full power. At 45°, you
[00:10:49] only get 70% of the power. If it's
[00:10:51] completely edge on, you shouldn't see
[00:10:53] anything. Although, the sun isn't a
[00:10:55] point source and technically neither are
[00:10:57] your panels. The sun's about half a
[00:10:59] degree across, so you'll always have
[00:11:01] some illumination there even if the
[00:11:02] panel is perfectly edge on.
[00:11:05] Now, obviously, you don't want solar
[00:11:06] panels to do this, but you do want your
[00:11:09] radiators to do this because those are
[00:11:11] trying to emit heat and not absorb it
[00:11:13] from the sun. And that's why you tend to
[00:11:15] try to put your radiator panels edge on
[00:11:17] to the sun as much as possible.
[00:11:20] But, when you're near the Earth, the sun
[00:11:22] isn't the only source of heating, right?
[00:11:25] The Earth is reflecting sunlight back
[00:11:27] into space, and even at night, the Earth
[00:11:29] is emitting thermal radiation into
[00:11:31] space. That's why it gets so cold on a
[00:11:33] clear night. The exact amount of heat
[00:11:35] that is being emitted varies depending
[00:11:37] upon your location on the earth and the
[00:11:39] weather, but on average it works out to
[00:11:41] about 200 watts per square meter at
[00:11:43] about 500 km. And it'll also change with
[00:11:46] altitude, getting lower as you get
[00:11:49] further away from the planet. And then
[00:11:51] there's the light reflected from the
[00:11:53] earth, right? And this varies a lot more
[00:11:55] depending upon the spacecraft's
[00:11:56] position. If it's in a low orbit at the
[00:11:59] subsolar point with the sun directly
[00:12:01] above and the earth directly below them,
[00:12:03] then the reflected light could be as
[00:12:05] high as 450 watts per square meter,
[00:12:07] about 1/3 of the sunlight uh passing in
[00:12:11] comes back at you from the opposite side
[00:12:13] to heat you up.
[00:12:15] So, unlike the sun, you can't really
[00:12:17] treat the earth like a point source.
[00:12:19] Even turning edge-on to the earth
[00:12:21] doesn't actually reduce the heating that
[00:12:23] much when you're in a very low orbit.
[00:12:25] And of course, Starlink satellites,
[00:12:27] their bus is actually required to face
[00:12:30] the planet below them and it receive all
[00:12:32] this radiation because the antennas are
[00:12:34] on the bottom and they're supposed to
[00:12:36] point to the customers below them.
[00:12:38] So, let's put all this together, all
[00:12:40] these numbers, to try to get the best
[00:12:42] and worst-case heating scenarios for a
[00:12:44] hypothetical data center in space. We're
[00:12:47] just going to look at the core satellite
[00:12:49] bus since that's the part that people
[00:12:51] are arguing over. I mean, I think we can
[00:12:52] all agree here that solar panels do in
[00:12:55] fact work in space, right? Okay?
[00:12:58] So, we have 20 kilowatts of power coming
[00:13:01] in and heating up that bus. Now, the sun
[00:13:04] is coming in and it's illuminating that
[00:13:06] satellite bus and the amount of heat
[00:13:07] changes based upon the angle of
[00:13:09] illumination and the emissivity of the
[00:13:11] surface being illuminated.
[00:13:13] Uh the light from the earth will vary
[00:13:16] throughout the day, but let's imagine
[00:13:17] that we are putting a data center into
[00:13:20] sun-synchronous orbit. That's the idea
[00:13:22] that started this whole thing. It's
[00:13:24] riding along the day-night terminator.
[00:13:26] The total illumination from the Earth
[00:13:29] is a combination of reflection and
[00:13:31] emission. It'll be about 400 W per
[00:13:33] square meter. There's a lot of potential
[00:13:34] variation here. I'm just using 400.
[00:13:37] It doesn't actually care that much about
[00:13:39] the angle of the spacecraft make that it
[00:13:40] makes to the surface because the Earth
[00:13:42] covers such a large part of the sky in
[00:13:44] lower Earth orbit.
[00:13:46] Now,
[00:13:47] remember our radiator is at 80 C. We've
[00:13:50] just chosen that number cuz it seems
[00:13:52] reasonable. That will emit at 880 W per
[00:13:55] square meter.
[00:13:57] The best case scenario is that we have
[00:14:00] the satellite bus over the surface of
[00:14:02] the Earth and the sun is coming to the
[00:14:04] side. So, we are essentially orienting
[00:14:06] the satellite bus edge-on to minimize
[00:14:08] the amount of solar illumination. So,
[00:14:10] for now, we will say that the solar
[00:14:12] illumination is zero and see how much
[00:14:14] margin we have. The Earth-siding face of
[00:14:16] the satellite, we're going to have 400 W
[00:14:18] coming up, right? And we have 880 W
[00:14:22] being radiated from both sides of the
[00:14:24] satellite. So, let's say we have go for
[00:14:27] a reasonably like emissive surface with
[00:14:29] an emissivity of about 0.8. It isn't
[00:14:32] that high. You can definitely do better,
[00:14:33] but 400 W coming from the Earth over
[00:14:35] half of the satellite area, which is
[00:14:37] 24.5 square meters, is 8 kW of extra
[00:14:41] heat.
[00:14:42] Add that into the 20 kW of electrical
[00:14:44] power being converted into heat and
[00:14:47] internet memes, of course, and we get 28
[00:14:49] kW, which is significantly less than the
[00:14:52] 34 kW of heat the structure will emit if
[00:14:56] it's run at 80 C.
[00:14:58] In fact, we can happily drop the
[00:14:59] radiator temperature down to about 65 C
[00:15:02] and it would still maintain thermal
[00:15:04] balance
[00:15:05] if we just were able to completely
[00:15:08] ignore the sun. And I sort of feel that
[00:15:09] the sun is kind of important here and we
[00:15:11] shouldn't be ignoring it. But yeah, if
[00:15:13] we have 6 kW of margin
[00:15:16] and we know the solar flux and we know
[00:15:18] the absorptivity of the satellite,
[00:15:21] we can figure out that the satellite has
[00:15:23] about a 10° dead zone, where if it goes
[00:15:26] beyond 10°, it'll start to absorb more
[00:15:28] than 6 kW of solar heating.
[00:15:31] So, that's actually pretty good. We can
[00:15:32] keep the satellite in a good position
[00:15:34] and keep it like cool. But, if we just
[00:15:37] keep the satellite bus edge on to the
[00:15:38] sun, you can go better. You could
[00:15:40] actually just put a bunch of shades
[00:15:41] along one edge and actually shade the
[00:15:44] satellite, reducing the heating a little
[00:15:45] more using very highly reflective
[00:15:48] surface along one side. So, if you have
[00:15:50] a flat spacecraft similar to a Starlink
[00:15:52] going in sun-synchronous orbit around
[00:15:54] the Earth, you and you can maintain the
[00:15:56] correct attitude using sun shades and
[00:15:58] reflectors and highly emissive radiator
[00:16:00] surface to handle the 20 kW of heat
[00:16:03] generated by all that computer hardware,
[00:16:05] you can do that fine as long as your
[00:16:07] computer hardware can handle 80° C. You
[00:16:10] can even drop the temperature a bit and
[00:16:12] lose some of that margin. And of course,
[00:16:13] if the solar panels move in the right
[00:16:15] way, the orientation could actually have
[00:16:18] you in a position where you're able to
[00:16:19] use your propulsion system without
[00:16:21] compromising the attitude you for and
[00:16:24] messing up your cooling. Now, this is an
[00:16:25] extraordinarily high-level analysis.
[00:16:28] There's a lot of room for real-world
[00:16:31] thermal engineering and analysis to
[00:16:33] understand this in more detail. What I'm
[00:16:35] really trying to show here is that it
[00:16:37] does not require ginormous radiators or
[00:16:40] some sci-fi level technology which
[00:16:42] hasn't been developed yet. This is
[00:16:44] showing that a Starlink satellite design
[00:16:47] is broadly in the right ballpark of
[00:16:49] viability for running computers. That's
[00:16:52] the best-case scenario. What about the
[00:16:54] worst-case scenario? Maybe there's good
[00:16:55] reasons why the satellite can't maintain
[00:16:58] edge-on attitude to the sun.
[00:17:00] Well, if you absolutely have to face one
[00:17:02] side of the satellite to the sun, you
[00:17:04] can cover it in highly reflective
[00:17:06] insulation. That'll deflect or sorry,
[00:17:08] reflect about 95% of the incoming
[00:17:10] radiation. That means the sun's only
[00:17:12] going to add 1 to 2 kW and really, it's
[00:17:15] only going to be about 1 kW when you
[00:17:16] account for the heat being emitted. Uh
[00:17:19] this isn't too bad, but really what is
[00:17:21] bad is that you lose that entire side of
[00:17:23] the satellite as the radiator. So, you
[00:17:25] lose half the radiator area, and in turn
[00:17:28] that means you need to you need to add
[00:17:30] actual extra radiation area. You need to
[00:17:32] have a radiator that sticks out of the
[00:17:34] backside and adds a little bit of
[00:17:35] surface area, but not a huge amount of
[00:17:37] surface area. It doesn't you know, it's
[00:17:39] not uh it's not going to break your
[00:17:41] design at least in this power range.
[00:17:44] But, how do you scale this up, right?
[00:17:46] 20kW used to be enough to power a full
[00:17:48] rack of computer gear, but we're seeing
[00:17:51] predictions now of 100kW per rack, and
[00:17:54] that's just one rack in a data center
[00:17:56] which might contain hundreds of racks of
[00:17:57] gear crunching numbers. The first
[00:18:00] renderings of space data centers showed
[00:18:02] massive solar arrays attached to a
[00:18:04] single hub with all the computers.
[00:18:07] But, a year later the more practical
[00:18:08] vision is individual satellites that
[00:18:10] communicate with each other to create a
[00:18:12] ginormous supercomputer. And as fast as
[00:18:16] these links are between satellites and
[00:18:18] different orbits, the light the
[00:18:19] information is crossing hundreds of
[00:18:21] kilometers in space rather than a few
[00:18:23] meters of a satellite network, and that
[00:18:25] increases the latency of interprocess
[00:18:27] communication, which can slow the
[00:18:29] ability for these computers to
[00:18:31] collaborate on certain types of
[00:18:33] problems. So, you you know, you're ended
[00:18:35] up optimizing for problems that can only
[00:18:38] be run on a single satellite. There is
[00:18:40] now an incentive to put as much hardware
[00:18:42] on a single satellite as possible.
[00:18:44] So, how would you put a 100kW rack in
[00:18:47] something like a Starlink satellite?
[00:18:49] Well, obviously you need bigger panels,
[00:18:51] probably something like 400 square
[00:18:53] meters worth. From a thermal point of
[00:18:55] view, there's now no longer enough
[00:18:57] surface area on a Starlink bus. So, you
[00:18:59] need to actually have it also deploy a
[00:19:01] radiator with about an extra 20 square
[00:19:03] meters of double-sided radiator maybe
[00:19:06] for every 20kW over that base 20kW.
[00:19:09] Again, assuming about 80° C.
[00:19:12] And once you start getting into these
[00:19:14] large deployable radiators, you really
[00:19:16] need to start thinking a bit harder
[00:19:18] about how you move the heat out to those
[00:19:21] radiators. Solar panels can be built
[00:19:23] like ultra-light weight wings because
[00:19:26] the only thing that they're moving
[00:19:27] around is electrons, but radiators, they
[00:19:30] need to move heat. And thermal
[00:19:31] conductivity is a lot slower than
[00:19:34] electrical conductivity, right? So, we
[00:19:36] are moving hot fluids in pipes out to
[00:19:39] the radiators and we're bringing cooler
[00:19:41] fluids back in.
[00:19:43] Water can carry about 4.2 kilojoules per
[00:19:45] kilogram per degree Celsius. So, if you
[00:19:48] have a 20 degree temperature difference
[00:19:50] between going out to the radiators and
[00:19:51] coming back, that needs about 1.2
[00:19:54] kilograms of water per second or 70
[00:19:57] liters of water per minute to remove 100
[00:20:00] kilowatts of heat.
[00:20:02] And you know, 70 liters per minute is
[00:20:04] not actually that bad, but the power
[00:20:06] required to move that amount of fluid
[00:20:08] really depends upon the geometry of the
[00:20:10] radiators and very specifically the
[00:20:12] geometry of the plumbing. There's like
[00:20:14] trade-offs to be made where the narrower
[00:20:16] you make the pipes carrying the fluid,
[00:20:19] the more surface area they have to lose
[00:20:21] heat, but the narrower they are, the
[00:20:23] more viscosity is going to tend to slow
[00:20:25] your fluid down and they therefore mean
[00:20:27] that the pumps need more power. You
[00:20:29] absolutely need to factor in the power
[00:20:31] that's going to be required for these
[00:20:33] pumps. You can spend a lot of energy
[00:20:35] pumping cooling fluid through really,
[00:20:36] really tiny channels in a radiator
[00:20:38] fighting against that viscosity. But by
[00:20:41] using really tiny holes, you then in
[00:20:44] turn reduce the amount of fluid that
[00:20:46] actually needs to sit inside the
[00:20:48] radiators and cool down. And that in
[00:20:49] turn reduces the overall satellite mass.
[00:20:51] So, there's a lot of trades to be made
[00:20:53] if you're designing a cooling system.
[00:20:55] And to be clear, these kind of cooling
[00:20:57] systems are needed even if you're able
[00:21:00] to just use the surface of the satellite
[00:21:01] for cooling. You still need to be able
[00:21:02] to move the heat away from the CPU cores
[00:21:04] and to to surface of the satellite. But
[00:21:07] when you get to massive deployable
[00:21:09] radiators, you have to start thinking
[00:21:10] about the inertia of that fluid and how
[00:21:13] it interacts with the radiators that
[00:21:14] you're trying to make as lightweight as
[00:21:17] possible.
[00:21:18] And on Earth, we use water, obviously,
[00:21:21] right? That works very well because it's
[00:21:22] pretty easy and pretty available. But,
[00:21:24] it water is probably not the best fluid
[00:21:26] to be used in space.
[00:21:28] If because, in particular, it can freeze
[00:21:30] and break pipes. The ISS uses ammonia
[00:21:33] and a Russian spacecraft use glycol. Uh
[00:21:36] there's things like two-phase coolers
[00:21:38] where the coolant vaporizes at the hot
[00:21:40] side and then is recondensing. Uh
[00:21:42] vaporization is actually really good
[00:21:44] because it's a very energy intensive, so
[00:21:46] you can reduce your mass flow rates to
[00:21:48] much smaller numbers. These are all like
[00:21:50] optimizations to be made, but the most
[00:21:53] important optimization that a spacecraft
[00:21:55] designer can make appears to be raising
[00:21:57] the radiator temperature. And because
[00:21:59] that is closely related to the operating
[00:22:02] temperature of the hardware, that could
[00:22:04] give a big advantage to someone who can
[00:22:06] design their own custom silicon that
[00:22:08] operates at higher temperatures. And
[00:22:10] Elon Musk has even talked about how
[00:22:12] getting chips that operate at 370 Kelvin
[00:22:15] or 97 Celsius makes increasing the power
[00:22:19] density of data center satellites far
[00:22:22] more viable. And incidentally,
[00:22:25] we've been talking about flat
[00:22:26] satellites. And of course, anyone that's
[00:22:27] worked in a data center knows that
[00:22:29] there's like these racks, right? The 48U
[00:22:31] 19-in rack, which is you're big and it's
[00:22:34] just dense with computers. How does that
[00:22:37] fit into a flat satellite? Well, it
[00:22:38] turns out that like 19-in rack is about
[00:22:40] 50 cm wide, it's about 1 m deep per
[00:22:43] unit. And if you've got a 24 and 1/2
[00:22:47] square meter satellite and you take all
[00:22:49] your 1U units and stack them out, it's
[00:22:51] actually roughly the same size. Now,
[00:22:55] this is obviously a really bad way to
[00:22:57] design a satellite, but I found the fact
[00:22:59] that the the
[00:23:00] you know, the Starlink satellite idea
[00:23:03] that I was using was almost exactly the
[00:23:05] same volume
[00:23:07] as a 48 U rack. Maybe I'm easily amused.
[00:23:10] So yeah, when I first saw the original
[00:23:12] Star Cloud renderings and read their
[00:23:14] white paper, I knew that they were
[00:23:15] making a lot of simplifications that
[00:23:17] would complicate turning their design
[00:23:19] and vision into reality. And I pointed
[00:23:21] those out, all right? The vision of
[00:23:23] massive data centers in orbit faces all
[00:23:25] sorts of technical challenges. Cooling a
[00:23:27] 5 gigawatt data center with giant
[00:23:30] radiators means pumping tons of cooling
[00:23:33] fluids around every second, even if you
[00:23:36] come up with a suitable two-phase
[00:23:37] cooling solution, right? But now the
[00:23:40] swarm of AI servers is becoming the
[00:23:42] solution that people are actually
[00:23:43] pursuing. Not that the costs are going
[00:23:46] to work out anytime soon, but one day
[00:23:48] they might. And maybe we will see the
[00:23:50] first migration of commercial industrial
[00:23:52] hardware from the surface into space.
[00:23:55] And maybe finally people will stop
[00:23:57] arguing over the ease of cooling
[00:23:59] computers and things in space, and
[00:24:00] instead start arguing about the real
[00:24:02] problem of cooling nuclear reactors in
[00:24:05] space. I'm Scott Manley. Fly safe.
