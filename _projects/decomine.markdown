---
layout: default
title:  DecoMine Project
description: A massively collaborative Java-based software development project at UQ with a cohort of nearly 200 students all working on the same codebase.
feature-img: decomine1.png
status: completed
---

In Semester 2 of 2015 I studied DECO2800 (Design Computing Studio 2 - Testing & Evaluation), a course I had heard was notoriously difficult and chaotic, but also a great selling point to future employers. So, under the guidance of the wonderful Dr Jim Steel, I took part in the massively-collaborative software development project with a cohort of nearly 200 other students.

The course involved the design and development of a simulator game with five interconnected sub-games, namely a marketplace, factory, farm, mine, and habitat. The aim was to develop a fully functional simulator which allowed for communication and trading of peons, wealth and resources through the centralised marketplace. I worked on the mining simulator with 60 other students, developing methods of transport such as ropes, ladders and elevators to assist peon travel around the mines and landscapes in the simulator.

<div class="col-md-6" markdown="1">
![DecoMine Game]({{ site.baseurl }}/img/decomine2.png)
</div>

<div class="col-md-6" markdown="1">
![DecoMine Interface]({{ site.baseurl }}/img/decomine3.png)
</div>

This provided me with a fantastic opportunity to apply my Java programming skills to a continuous integration project with a strong emphasis on unit testing, where I was able to learn far more than I would have just being lectured with content. At the end of the 13 week period, the cohort collectively contributed over 9000 commits on 165 feature branches, with the project being a huge success. I contributed 63 commits and 6,782 lines to the mine simulator project, the third highest in the project, and as a result of my involvement was selected as one of four students who demonstrated the finished project to the university's industry partners and the general public. This provided me with a fantastic networking opportunity which I valued greatly. Looking back on the course, I am incredibly proud of my own personal progress throughout the semester and also of the finished project.

##### Collision Detection and Climbing
* * *
The first phase of my implementation extended upon the existing collision detection system and the `moveTowards()` functionality present in the WorldEntity class. It was incredibly basic and simply checked if the detected collision was an instance of Transportation, if it was, the peon’s position was moved up by one until the collision was no longer registered. I also implemented functionality to change the peon’s speed when they were interacting with transportation. Ropes moved the peons at their default speed, Ladders moved the peon twice as fast as normal, and Elevators moved peons four times as fast.

##### Transportation Tasks
* * *
A little while into the project my code for peons climbing was migrated to a separate Climb Transportation class to better suit its role in the game. I replaced the climbing code in WorldEntity with code to switch the peon’s task and begin climbing, whilst storing their previous task so it could be resumed upon finishing climbing. As development of the game progressed, I extended the climbing task to cater for a number of different scenarios, explained below:

1.  Peon has reached their destination level, so exit the ladder on the correct side
2.  Peon still needs to climb up
    *   Peon wants to climb higher, but no higher ladder exists within reach, so exit the ladder on the correct side
    *   Peon wants to climb higher, and a higher ladder exists within reach, so begin a new task to climb that ladder
3.  Peon still needs to climb down
    *   Peon wants to climb lower, but no lower ladder exists within reach, so exit the ladder on the correct side
    *   Peon wants to climb lower, and a lower ladder exists within reach, so begin a new task to climb that ladder
4.  Peon is climbing to a point on the ladder, not a point on the map, so make them stand still when they reach their destination ladder

##### Random Events
* * *
I came up with two ideas for new random events and decided to implement them myself, extending upon the framework created by Team Reddy. The first random event I created was called Rope Upgrade and involved mapping every existing rope entity in the current world, removing them, and inserting ladders into the positions recorded. The second random event was similar, but involved upgrading all ladders to elevators.

##### Overall Contribution
* * *
*   Collisions with transportation & climbing functionality
*   Re-write peon destinations to include y position
*   Restore peon’s previous task when finished climbing
*   Peons climb transportation on click
*   `getNearestYabove()` & `getNearestYbelow()` to get closest transport
*   Added climbing animations
*   Make peons exit transportation at destination Y position, not highest
*   Prevent transportation showing its name and health bar
*   Prevent right clicking entity to pick it up from affecting transportation
*   Prevent peons from climbing non-continuous ladders
*   Add Transportation random events
*   Revamp `ClimbTransportation` task to deal with numerous scenarios
*   Clear all tiles in the path of dynamic transportation
*   Write `transportContextController` & `transportContextControllerHandler`

![Github contribution]({{ site.baseurl }}/img/decomine4.png)  

You can find more examples of projects I've done in the area of game development [here!](http://astridfarmer.com/gamedevelopment)
