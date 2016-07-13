---
layout: default
title:  Physical Computing
description: In this course I built a large-scale interactive musical experience that allows people to experiment with music without requiring any skill.
feature-img: physicalcomputing.png
status: completed
---

The Physical Computing and Interaction Design course (DECO3850) afforded me the opportunity to explore the design space of creating playful and open ended interactions in everyday life. Throughout the following 13 weeks, we would split into teams of four and work towards building an installation to exhibit at the final showcase on May 31st, 2016.

Our goal in building MozART was to provide people with an interactive and immersive experience which would allow them to create and interact with music without requiring any knowledge or experience. Allowing people to create and augment music in this manner, or collaboratively with other people in the space, helps to break down some of the barriers that may have been preventing these people from expressing themselves musically in the past. By removing the factors that often prevent people from engaging in music, fear and lack of expertise, MozART aims to explore the way people interact with music and each other when they find themselves capable of much more than they ever have been before.

<div class="col-md-6" markdown="1">
![Physical Computing exhibit](/img/physicalcomputing2.jpg)  
</div>

<div class="col-md-6" markdown="1">
![MozART visuals](/img/physicalcomputing3.png)
</div>

##### Kinect Depth Tracking
* * *
Tracking the depth of the spandex canvas was the core of our program, upon which everything else was built, so it was essential to make this section as efficient and accurate as possible. I began with a simple threshold, comparing each pixel in the data stream to the threshold, effectively filtering only the areas which someone was pushing on. After initially finding the average point of all pixels in each of the three sections and using these points to generate the music and visuals, I realised that I would need to find a more effective way of tracking multiple touch points individually. Despite being a very time consuming process, I eventually developed proper blob tracking functionality, creating a very precise way to track touches.

In developing the blob tracking, I inadvertently gave myself all the tools I would need to modulate the music based on these blobs. I was able to quite easily track the individual location, width, height, speed, direction, depth, and total number of blobs, which opened up a huge number of possibilities for our project moving forward. I was pleasantly surprised with just how well suited the Kinect was to our specific problem space, and with how much I was able to achieve in just a few weeks.

##### Kinect to Visuals
* * *
One of the three main areas I worked on was setting up the communication between the Kinect and the visuals which were to be displayed on the spandex canvas using rear-projection with a short-throw projector. I tried many different approaches over the course of the semester, to varying degrees of success, but finally came up with a solution roughly 3 weeks before the final exhibit. After blobs are successfully interpreted and tracked using the Kinect data, I was able to set up a local OSC Server and Client to send and receive the messages required to generate the visuals. To clarify, "Open Sound Control (OSC) is a protocol for communication among computers, sound synthesizers, and other multimedia devices that is optimized for modern networking technology" ([Open Sound Control Organisation](http://opensoundcontrol.org/))

I made the decision to use OSC to facilitate the data transfer since the MSAFluid library already had inbuilt support for the TUIO protocol, which is encoded using the OSC format. TUIO is built to "allow the transmission of an abstract description of interactive surfaces, including touch events and tangible object states. This protocol encodes control data from a tracker application (e.g. based on computer vision) and sends it to any client application that is capable of decoding the protocol" ([TUIO Organisation](http://www.tuio.org/)). Using the TUIO protocol allowed us to take advantage of the TUIO demo version of MSAFluid and modify that to our liking, rather than starting from scratch. Other examples of using a Kinect with MSAFluid had also use these same technical choices, however, there was no existing examples compatible with the Kinect for Windows V2 meaning I had to write my own program to facilitate this.

##### TUIO Protocol
* * *
As stated prior, once the blobs have been successfully tracked from the Kinect data, I had to translate that information into TUIO messages which would be sent in bundles via the TUIO port 3333 on the server to the receiving TUIO client. TUIO bundles follow this format:

    /tuio/2Dcur source application@address   
    /tuio/2Dcur alive s_id0 ... s_idN   
    /tuio/2Dcur set s_id x_pos y_pos x_vel y_vel m_accel   
    /tuio/2Dcur fseq f_id

The first message defines the source of the data, and the address it has been received from. It was not important in my case, since there was only one data source, however I still kept it in for clarity. The second message is an 'alive' message which contains the unique session IDs of each blob being tracked. Once each bundle is received, these 'alive' messages are checked against the previous messages to determine the life duration of each blob. Following that, a 'set' message will be sent for every blob tracked, along with the x and y position, the x and y velocity, and the motion acceleration of the blob. Finally, a 'fseq' (frame sequence) message will be sent with an incremented ID to signify the end of the message bundle or to mark redundant bundles.

##### Kinect to MIDI to Ableton Live
* * *
Translating the Kinect data into successful music manipulation was the lengthiest process during the semester, and was also the most crucial to the success of the project. The goal was to effectively turn the spandex canvas into a giant MIDI controller which was not an easy task, and which had not been done before on the size and extent we were aiming for. In just a few short weeks I progressed from sending simple MIDI notes through a virtual MIDI port into Ableton Live, to sending much more complex MIDI controller change messages with dynamic values based on the depth and location of the blobs picked up by the Kinect. Using Ableton Live was perhaps the steepest learning curve I faced in the project, and understanding exactly what data I had to send and through which channels was a daunting task.

<div class="col-md-6" markdown="1">
![Ableton Live interface](/img/physicalcomputing4.png)  
</div>

<div class="col-md-6" markdown="1">
![Ableton Live interface](/img/physicalcomputing5.png)
</div>

I developed the system to send the MIDI messages in a way that I felt was interesting being a non-musician, and tried to retain as much as possible a dynamic approach that would not result in the same output for every user. I chose to randomise the selection of instruments, tracks, and effects to create a truly exploratory experience, which I felt played out well with users who were then able to play with the music in a way that was constantly changing.

Experiencing the huge amount of possibilities MIDI provides in Ableton, and how easily this can be controller externally using the Kinect has been an amazing experience. I learned a significant amount about digital music creation and manipulation, which I feel has helped me grow as a designer and developer by using my code in ways I have not been able to in any other university course.

##### Final Exhibit
* * *
The final product we exhibited at the showcase was a huge success. After being given a separate room away from other groups, we were able to take advantage of the darkness and also some extra couches. We were also able to set up a livestream on Twitch which we displayed outside in the main area to encourage people to come and visit our installation. As the day continued, we got a lot more visitors who had heard via word of mouth to check us out, which was very encouraging.

The reception we received from people attending the event was fantastic, with a lot of people keen to talk to us more about our work, rather than just try it and move on to the next one. We also got a lot of suggestions about how it could be used in other situations and for other purposes. Those guests in attendance who had musical experience could see the implications this type of project could have if developed further, and also had a lot of suggestions for us concerning that. We were lucky enough to be invited to show our work at the Girls in Computer Science event, UQ Open Day, and at Sheldon College, with a possibility to continue working on the project next semester with music students.

<iframe width="100%" height="400px" src="https://www.youtube.com/embed/MKYuEVxEvtE" frameborder="0" allowfullscreen=""></iframe>
