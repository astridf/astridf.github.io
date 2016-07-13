---
layout: default
title:  Game Development
description: Some of the projects I've worked on involved developing games using various programming languages, read more about those here.
feature-img: patterndrop1.png
status: completed
---

##### DECO2300 (Digital Prototyping)
* * *
**Assignment specification:** "Create a mashup of 2 games - choosing from pencil & paper games, board games and arcade games. Your new game should be interactive & digital in form and must involve some form of non-traditional, novel physical interaction (no keyboard, mouse or existing game controller). It should capture & combine the key elements of each of your games into something unique and captivating."

My concept was a mashup of Cows & Bulls and Tetris, and I chose these two games because I played both of them when I was younger, and could see a lot of potential for overlap between the two. Cows & Bulls is a strategy guessing game in which users attempt to guess correctly a sequence of letters or numbers. Tetris is a classic childhood game for many people, and therefore doesn't require as much of an explanation.

<div class="col-sm-6" markdown="1">
![Pattern Drop UI](/img/patterndrop1.png)  
</div>

<div class="col-sm-6" markdown="1">
![Pattern Drop testing](/img/patterndrop2.png)  
</div>

Pattern Drop takes from the code or pattern guessing element of Cows & Bulls, requiring users to try and guess a pre-determined combination of colours by changing blocks until the correct pattern is chosen, which is where elements of Tetris come in. Users interact with the blocks in the same way they would in Tetris, moving them left and right as well as dropping them. Another aspect drawn from Tetris is the idea of blocks stacking up towards the top of the screen.

The game was built using ActionScript 3, and the game controller consists of two boxes, one large empty box and one tiny box held by the player, and a Makey Makey kit. To move left or right, the user needs to tap the small box they are holding on the left or right inner side of the bigger box. To change the colour of the block, they tap the small box on the inner roof of the bigger box, and to move the block down faster, they tap the inner bottom of the large box.

##### DECO1800 (Design Computing Studio 1 - Interactive Technology)
* * *
**Assignment specification:** "In teams, you will be asked to conceptualise, refine and implement a web-based application that presents data hosted on the National Library of Australia’s Trove portal in an engaging & interactive manner.  You should aim to go beyond the simple search paradigm that Trove currently has and that shed light on rarely visited corners of Trove. Your challenge is to explore the data as it is and to generate interesting ways of focusing, filtering, searching, connecting &/or presenting the data."

The web application we chose to design is a game targeted towards children in grades 3 or 4, who are learning about famous landmarks in their geography class at school. The purpose of the game is to deliver Trove content to these children in a new way, which will allow them to learn or revise content learned at school. We located some specific points in the current National Curriculum for grades 3 and 4 upon which we built our application:

_"By the end of Year 3, students can identify Australia's states and territories, and Australia’s major natural and human features", and "By the end of Year 4, students describe and compare the characteristics of places in different locations at the national scale"_

<div class="col-sm-6" markdown="1">
![Landmark Flipper UI](/img/landmarkflipper1.png)  
</div>

<div class="col-sm-6" markdown="1">
![Landmark Flipper planning](/img/landmarkflipper2.jpg)  
</div>

The user begins by selecting the topic they wish to play, and choosing the level of difficulty they wish to play on. They are then shown a blank grid of tiles which they are able to reveal one at a time. The aim is to guess the famous landmark in as few flipped tiles as possible, and to stay within the time limit. Three options of the landmark's name are provided, and the user must choose the one they believe is correct. When guessed correctly, further information about the landmark will be displayed, allowing the user to learn more about each image. There will also be a scoring system in place, rewarding the user for correct guesses in the fewest amount of tiles flipped, and users will be encouraged to try and beat their own scores by playing the game again.

The game we created aims to spark more interest in the vast amount of resources Trove has to offer. The primary form of content being sourced from Trove was images retrieved using Trove’s Web API, which were chosen specifically, and categorized according to their difficulty. To support these images, small descriptions were also be sourced from Trove so that this information could be provided to users to serve as hints and further information to assist learning.

Another example of my work in the area of game development is the DecoMine Project, [read more about that here!](http://astridfarmer.com/decomine)
