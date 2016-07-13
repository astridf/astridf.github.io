---
layout: post
title:  More prototype progress...
date:   2016-04-17
category: Physical Computing (DECO3850)
author: "Astrid Farmer"
tldr: Had three more prototype iterations this week, and finally tamed Ableton!
thumbnail: midimap.png
---
So this week I started working on the prototype, mainly to get the Kinect stuff working so everyone else could start working on their bits (construction, music, visuals), but also because I'm way more invested in this course than I expected to be, and I'm really excited to get everything up and running.
I started off simple, just tracking the data sent from the Kinect and checking each pixel to see if the depth was infront of a certain threshold. In the final exhibit, the threshold will be set to be just infront of the spandex material, so that it will only register when someone is actually pushing on it. At this stage, I was not concerned with manipulating anything based on the depth beyond checking the threshold, this will come eventually, but it is not a priority yet. Once I could get all the pixels infront of the threshold, I was able to get the average point of all those pixels using an example I found, and keep track of the x and y position of it. I then used the x and y position to modify the pitch of a MIDI note being sent to the inbuilt Microsoft GS Wavetable Synth, since at this point Ableton Live had some sort of vendetta against me and would not co-operate. Here's a video of me testing the first version of the prototype:

<iframe width="100%" height="480" src="https://youtube.com/embed/BbxmH9y3R-E" frameborder="0" allowfullscreen></iframe>

Next, I managed to coax Ableton into finally doing what it was told, and I was able to finally make something that didn't sound awful. I also implemented a second and third instrument, by splitting the canvas into three sections and checking where the x position of the tracked point was. Based on that, I set up the same message to send a MIDI note with a pitch based on the location of the dot, except this time I set up three virtual MIDI ports. I created three tracks in Ableton, each one listening to a different MIDI port, and each one with a different sound so I could differentiate between them. Here's a video of the second version:

<iframe width="100%" height="480" src="https://youtube.com/embed/bJAximSfdGs" frameborder="0" allowfullscreen></iframe>


Finally (as in literally 20 minutes ago), I managed to get everything working. Now, there are still three sections corresponding to different instruments, however, you can now control them individually. To do this, I set up three new functions, each to track the registered pixels in their own sections and then to send the corresponding MIDI notes based on their average point. I also fixed the problem of some random stray pixels causing MIDI notes to play on their own, by not playing a MIDI note unless there was more than 30 pixels registered at the time. Here's a video of that:

<iframe width="100%" height="480" src="https://www.youtube.com/embed/yIP5eRzAqQI" frameborder="0" allowfullscreen></iframe>

I'm very happy with the progress I have made, especially now that it means we don't have to fake anything behind the scenes with our prototype. We hope to spend the rest of the week improving the music aspect, since it sounds pretty awful at the moment, and also getting some dynamic visuals projected onto the mini spandex sheet the tutors gave us.
