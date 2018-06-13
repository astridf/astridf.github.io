---
layout: post
title:  It's crunch time - Week 11
date:   2016-05-20
category: Physical Computing (DECO3850)
author: "Astrid Farmer"
tldr: It’s all smooth sailing for Team Good Vibes, the visuals are finally fixed!
thumbnail: mozartsetup2.jpg
---

 <iframe width="100%" height="480" src="https://www.youtube.com/embed/X06b1ftx-RI" frameborder="0" allowfullscreen></iframe>


 So week 11 has finally rolled around, and amongst a lot of panicking and desperation in the workshop from some other groups, it's all smooth sailing for Team Good Vibes. Well, it appears that way for now. Inevitably we will be thrown a couple of curve balls in the next two weeks, but we are confident it'll all work out for us.  

 As I spoke about in my last blog post, we have finally fixed the visuals that will be projected onto the spandex, so anything we do from here on out in the visuals aspect will just be extra little features that may add to the experience. Knowing that it is currently in a form where we could present it tomorrow and get away with it is definitely reassuring. Due to the nature of the MSAFluid library, we technically have three different versions of the visuals which we can switch between. They are all quite different, and although we will likely primarily stick with Mel's version, we are considering adding foot pedals which would allow the user to switch. This doesn't really add anything to the experience besides looking cool, but it would only require 10 minutes with a Makey Makey to set up, so we figure why not :)  

 Naomi is still hard at work churning out some funky tunes for us to play with, which we hope to have completed by Friday so we can do some user testing with the finished product. In the meantime, we also filmed a few scenes for our video on Tuesday. Since I had only fixed the visuals the night before, and didn't have the version on my laptop that was integrated with the Kinect, we settled for the basic mouse controlled version which was sufficient for mimicking the final interaction at least for the draft video. I would expect that we may re-film us interacting with the installation when it is fully set up on Friday or next week, but we have what we need to submit the draft video which is due on Friday. While we were filming on Tuesday, we did have a couple people come up and want to play with our installation as is, so we think that's a good sign.  

 ![MozArt Setup]({{ site.baseurl }}/img/blog/mozartsetup1.jpg)  

 ![MozART Testing]({{ site.baseurl }}/img/blog/mozartsetup2.jpg)  

 I still have a few minor things to fix in my code, and one of those things is sending MIDI messages to mute/unmute tracks depending on whether any blobs are present. We are also looking into controlling the volume of instruments to improve the interaction. Another thing I will need to do is limit the height that the Kinect reads, or at the very least adjust it when it goes to send the position of blobs to the visuals, because at the moment they are working with different dimensions which means that the visuals do not align properly to where users push on the screen. I know exactly how to fix it, it's just a matter of me getting around to it. Daniel has also set up the twitter bot connected to a foot pedal with the Makey Makey which captures the visuals when the pedal is pressed and tweets it out on our twitter page ([UQ Mozart](https://twitter.com/uqmozart)) along with a caption. Again, this is just another fun feature we decided to add, the purpose of which is to let people capture the visuals they have made.
