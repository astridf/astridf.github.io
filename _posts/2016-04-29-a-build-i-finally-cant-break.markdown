---
layout: post
title:  A build I can't break!
date:   2016-04-29
category: Physical Computing (DECO3850)
author: "Astrid Farmer"
tldr: We constructed the physical frame for the spandex, and now we can't stop playing with it...
thumbnail: jenkins.png
---

On Thursday, the day had finally come where we were able to construct our fully-fledged installation. It was nice working on a build project for once, and there were surprisingly no injuries, though probably copious amounts of health and safety violations. I will say, this is the first build where I haven’t had a visit from good old Jenkins when I broke something. DECO2800 still gives me nightmares.

![Jenkins]({{ site.baseurl }}img/blog/jenkins.png)

We were lucky enough to have the workshop pretty much to ourselves most of the day, which is more for the sake of other people’s ears rather than having our own personal space (using a hacksaw on metal is not the nicest sound in the world). Fortunately we were able to get all the materials we needed besides the spandex for free from my grandfather, so we were not too concerned if we made mistakes. Everything went to plan (mostly) and now we have a funky fresh frame which holds our beautiful spandex perfectly.

![Finished build]({{ site.baseurl }}img/blog/finishedbuild.jpg)

Because of our design, our initial prototype of the software could be directly scaled to our finished build simply by moving the kinect back a metre or so and adjusting the threshold. A few minor adjustments will need to be made once we figure out the perfect distance and setup for our projector and kinect.

And now it’s time for me to get back to work on the programming side, which I’m planning to spend my long weekend finishing off (what a nerd…). My previous version used in the recent prototype was a rushed job to test the ideas we came up with, and isn’t practical in the long term. It was checking each pixel of the kinect depth map against a certain threshold and colouring it accordingly, from there all the pixels infront of the threshold were averaged to find a central point for each of the three instruments. This worked brilliantly for the prototype, but it is time to scale up. I’ve now moved on to blob detection, which looks a little something like this:

![Blob Detection]({{ site.baseurl }}img/blog/blobdetection.png)

Approaching the multi-touch functionality this way will simplify the process immensely, especially with the use of a couple basic open-source libraries. We are currently having discussions about the way we will use these blobs to generate the MIDI messages, though we have a few solid ideas which will likely be refined in the next few days. This approach will give us a bunch of very useful variables such as the height/width of blobs, their location, speed, direction, depth, and the total number registered at any one time. Now it’s just time to figure out exactly how we want to use them.
