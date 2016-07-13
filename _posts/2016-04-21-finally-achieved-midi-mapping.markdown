---
layout: post
title:  Finally achieved MIDI mapping!
date:   2016-04-21
category: Physical Computing (DECO3850)
author: "Astrid Farmer"
tldr: Can finally map MIDI values to different effects rather than just sending static notes, woo!
thumbnail: ableton.png
---

I had a little extra free time on my hands today, so after having a few unsuccessful attempts at Midi mapping over the week, I decided to give it one last shot, and it worked! I realised my mistakes were that I was sending MIDI notes rather than MIDI control change messages and I was also sending them all through one channel. I've had a bit of a struggle learning Ableton, but I think I'm slowly figuring it out. I managed to get the Y position of the blue dots to each send MIDI control change messages to different channels, and then I was able to use the MIDI mapping feature in Ableton to link the frequency of each sample back to the Y position.

We're going to be demonstrating our prototype in the session tomorrow, so stay tuned for an update on that.

<iframe width="100%" height="480" src="https://www.youtube.com/embed/RhxZefhz4NU" frameborder="0" allowfullscreen></iframe>
