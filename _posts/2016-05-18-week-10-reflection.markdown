---
layout: post
title:  Week 10 Reflection
date:   2016-05-18
category: Physical Computing (DECO3850)
author: "Astrid Farmer"
tldr: Worked up my own version of TUIO blob tracking, basked in my own glory briefly.
thumbnail: msafluid.jpg
---
Week 10 was a majorly busy week for team Good Vibes, as is expected this close to the showcase and to the end of semester. We have hit the point where the core of our installation is perfect, and now we're moving on to adding all the extra features we put on the back burner while building the rest of our installation.  

As usual, I've still been working hard on the behind-the-scenes integration of the Kinect with the audio as well as the visuals, so I have really been feeling the pressure to make sure everything works perfectly since neither the music nor the visuals can proceed without the Kinect. Thankfully I managed to set up a functioning prototype much earlier in the semester so Daniel, Naomi, and Mel have been hard at work on their own sections ever since. I also created a Kinect simulation program which the others were able to use without having the Kinect on them at all times. Since it is also quite time-consuming and annoying to get up and test the interactions with the Kinect every time I thought I changed or fixed anything in the code, it proved to be a very valuable tool for debugging and just generally churning out the code quicker than I otherwise would be able to.  

One major problem I encountered was trying to properly integrate the Kinect with the MSAFluid visuals. The problem was mainly due to my laziness, since I was trying to find an existing solution or program to connect the two, though everything I came across was very outdated and was specifically designed for the old Kinects for the Xbox 360s. I spent a lot of time investigating other options, but came up empty-handed unfortunately. I realised I was going to have to do it myself from scratch, so I tried to cut corners where possible (definitely regret that now). What I came up with was a simple program to send OSC messages from the Kinect project to the MSAFluid project, and whilst this in theory should have worked, since MSAFluid was designed to use the TUIO protocol which is encoded using the OSC (Open Sound Control) format, I had to re-work a lot of the existing functions to fit.  

Unfortunately, whilst my solution did in fact work, there was an underlying problem which pretty much made it impossible for the visuals to work without going crazy when it was running with my attempted OSC solution rather than straight up TUIO.  

And by crazy, I mean this:
<iframe width="100%" height="480" src="https://www.youtube.com/embed/eqm3qiEYW2g" frameborder="0" allowfullscreen></iframe>

So I finally decided to just bite the bullet and work up a new blob tracker that sends TUIO from the Kinect for Windows V2. Such a thing didn't exist for the platform and use case I was working with, so I had to start from scratch, but now it does!  

* * *
Just a quick explanation of TUIO for clarity (from the TUIO protocol specification website):  

The TUIO protocol is encoded using the Open Sound Control format, which provides an efficient binary encoding method for the transmission of arbitrary controller data. Therefore the TUIO messages can be basically transmitted through any channel that is supported by an actual OSC implementation. The default transport method for the TUIO protocol is the encapsulation of the binary OSC bundle data within UDP packets sent to the default TUIO port number 3333\.  

The TUIO protocol defines two main classes of messages: SET messages and ALIVE messages. SET messages are used to communicate information about an object's state such as position, orientation, and other recognized states. ALIVE messages indicate the current set of objects present on the surface using a list of unique Session IDs.  

To avoid possible errors evolving out of packet loss, no explicit ADD or REMOVE messages are included in the TUIO protocol. The receiver deduces object lifetimes by examining the difference between sequential ALIVE messages.  

In addition to SET and ALIVE messages, FSEQ messages are defined to uniquely tag each update step with a unique frame sequence ID. An optional SOURCE message identifies the TUIO source in order to allow source multiplexing on the client side. To summarize:  

- Object attributes are sent after each state change using a SET message  
- The client deduces object addition and removal from SET and ALIVE messages  
- On object removal an updated ALIVE message is sent  
- FSEQ messages associate a unique frame id with a bundle of SET and ALIVE messages  

So the TUIO bundle looks a little something like this:  

    /tuio/2Dcur source application@address  
    /tuio/2Dcur alive s_id0 ... s_idN  
    /tuio/2Dcur set s_id x_pos y_pos x_vel y_vel m_accel  
    /tuio/2Dcur fseq f_id  

* * *

After a solid day and a half trying to work it all out and get it running smoothly turning blobs into TUIO cursors it finally worked! What this means is that the Kinect for Windows V2 is now compatible with MSAFluid where it previously had not been. When I finally ran it again with MSAFluid, it worked perfectly. And by perfectly, I really do mean perfectly. I was so happy I pretty much spent the rest of the day basking in my own glory. This was the last main hurdle we had, since the music/MIDI problems had also been solved, so now it'll be smooth sailing to the exhibit (hopefully...)  

Here's a video of it running correctly:

 <iframe width="100%" height="480" src="https://www.youtube.com/embed/nfmUMzDKkEU" frameborder="0" allowfullscreen></iframe>
