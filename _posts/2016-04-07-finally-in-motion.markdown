---
layout: post
title: Finally in motion - Week 5
date:   2016-04-07
category: Physical Computing (DECO3850)
author: "Astrid Farmer"
tldr: Mid-sem break, and we almost have a fully formed idea for DECO3850, time to prototype!
thumbnail: kinect.png
---
It's been two weeks since my last post, and a lot has happened. The Easter break gave us the opportunity to kick off our shoes and forget about the looming showcase, which the more I think about, the more I realise it's not that far away. Even with the Easter break, my group still put in the hard yards and pushed on with our idea, which is shaping up to be something we're all pretty excited to build. My group is tackling Musical Performance, for those unaware.

We are coming very close to a fully formulated idea, with just a few details left to settle on. Our installation will consist of a large spandex wall, likely 3 metres wide and approximately 1.5-2 metres tall, and will feature a Kinect sensor and a projector hidden behind the wall. Taking advantage of the rear-projection capabilities of the spandex material, a real-time animation will be projected onto the wall which will respond to the touch of users. The Kinect sensor will be used to pick up the changes in the depth of the fabric, triggering a change in the animation to account for the user's touch. It will also pass data to Ableton Live, where the real show takes place.

Touching and pushing on the spandex will generate music played back in real time, allowing the spandex wall to act as a musical instrument of sorts. Different sections of the spandex will trigger different instruments, and the movement of the user will manipulate and change the sound being generated. This music, paired with the visual animations, we hope will give the user an immersive musical experience that will allow them to have a turn at playing music without any musical expertise.

My particular role in the group is to take care of the Kinect, which I'm looking forward to. The Kinect will transfer its data at this stage most likely to the Processing IDE where we will have set up scripting to handle the flow of data. The interpreted data will be sent from Processing using the OSCp5 library to the OSC interface for Ableton Live called LiveOSC where it will be used to generate the music. The visuals will likely be generated using an open-source library in Processing called MSAFluid which is used for solving and displaying real-time 2D fluid simulations.
