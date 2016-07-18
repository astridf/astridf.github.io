---
layout: post
title:  Yet another testing session
date:   2016-05-26
category: Physical Computing (DECO3850)
author: "Astrid Farmer"
tldr: The Mac Mini will be the death of us, reworked the MIDI code too
thumbnail: midi.jpg
---

 <iframe width="100%" height="480" src="https://www.youtube.com/embed/KD-_GSuW3mo" frameborder="0" allowfullscreen></iframe>

 Once again we set up everything for the installation, and once again I was eternally grateful to the gods of 3850 that we managed to finish up all the code, visuals, and music last week. I've found myself at the point in the semester where I thought everything would be going wrong and I would be stressed out of my mind. And yet here I am, thinking of extra little features I could add in before next Tuesday, only stressed about the lack of things I have to stress about. But of course, it hasn't been easy getting to this point.  

So like I said, on Tuesday we set up MozART to have another testing session, just to make sure there was nothing that needed fixing. For some reason, every time we run the project on the Mac Mini, something changes and we have no idea why. Last time, it was the display size and issues with speakers not being automatically recognised, this time the visuals decided to draw way more connections between all the different vertexes. I can't really complain though, we've kind of accepted it as a cool new feature, so hopefully it doesn't randomly disappear. I found it to be cool to have more sticks/lines being drawn, because they tended to connect the blobs being displayed, meaning that it essentially was drawing lines between multiple users. It also looked pretty cool!  

I also re-worked a small section of my code to map the MIDI values in three sections of the canvas, rather than the whole thing. Since MIDI messages are sent with a value of anything between 0 and 127, you would have to drag a blob diagonally from corner to corner to hear the whole effect. Since it is quite hard to do that without losing the blob, and most people just stayed and moved in a small area, having multiple mapping areas allows you to hear the full effect with a much smaller movement. We tested this on Tuesday, and found it still a little bit hard to hear the changes in music. To combat this, we will be changing the volume of tracks based on whether or not an effect is being applied to it (which occurs when a blob is detected, and the XY position of the blob determines the MIDI value), so you will hear a much more noticeable difference and the tracks you are manipulating will be highlighted more.  

We still have a few minor fixes to add in to the visuals, courtesy of Mel, and we will continue playing around with the music and effects until it is perfect for next Tuesday!
