---
title: "Devil dust"
permalink: /personal-projects/devil-dust
author_profile: true
---
---
##### Genre: Twin stick shooter, arcade, adventure, 3D
##### Team size: 2
##### Timeline: 1 week ( for stop killing game community jam)
##### Released: july 2026
##### Platforms: Web browser/Windows
##### My role: Game designer, Level designer, Programmer
##### Tools: Godot, Microsoft word, Microsoft Excel
---
We wanted to make a casual, fun game inspired by Dune world and old retro twin stick shooter games. The game should be simple to learn and follow but with its own challenges.

Play the game here: [link](https://aethewn.itch.io/dust-devil)

![trailer](/images/dust-devil-trailer.gif)

# Responsibilities
- Designing the game mechanics
- Designing levels
- Writing & maintaining GDD
- Helping with the programming of the game
- Designing UI/UX

# Player car

I was responsible for the car movement in this project.

We wanted the car to feel responsive and feel good when driving and jumping on top of the dunes, and give them an immersive experience.
Since the timeline for the project was short we used a Godot plugin for vehicles but we had to modify it for the game. We added trailing shaders so it would leave trailing mark on the dunes and enhance the feeling even more

# Designing the level

My goal for this level was to create a retro style desert area surrounded by mountains.
To design the level we used Terrain3D plugin with a free dune preset.

I scattered the enemies across the map in groups for easier balancing due to short jam time.

# Enemies
For the infantry units we were looking for patrolling units that would follow you if you get close enough and follow/shoot you until you're out of the range. While developing the game we realized lag/jittering. To solve that issue we implemented object pooling on the infantry units to increase the performance. The game has over 100 3D models in the same terrain. To increase the performance even further we had to remove the 3D model and use simple geometrical shapes. To make up for the aesthetics we used pixelated filter to add retro feelings to the game and hide the cubes.

