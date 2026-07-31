---
title: "Relay rush"
permalink: /personal-projects/relay-rush
author_profile: true
---
#### Genre: arcade, adventure, puzzle, 2D, Top-Down
#### My role: Game designer, Level designer, Programmer, Pixel artist, Audio designer
#### Tools: Godot, Libresprite, Ableton live, Microsoft word, Microsoft Excel, Photoshop
#### Team size: Solo project
#### Timeline: 1 month
#### Platforms: Web browser


I wanted to make a game inspired by "Cross the road" games but with a twist of having tower defense mechanics in it but keep the game easy to learn and fun to play. It resulted in creating Relay rush.

[Here's the link on Itch.io to try the game!](https://sassanthedev.itch.io/relay-rush)

![Trailer](/images/relay-rush-trailer.gif)

# Responsibilities
- Designing the game mechanics
- Designing levels
- Writing & maintaining GDD
- Programming the game
- Creating the art assets, audio & soundtracks
- Creating UI


# Grid based movement

Inspired by "Cross the road" games, I wanted to create a grid-based movement system for the player character. This design choice made me realize that limitations can often inspire creativity. I implemented movement cooldowns that vary depending on the package the player is carrying and the type of tile they are standing on. Grid movement forces players to commit to decisions, making every tile a tactical choice instead of allowing continuous dodging.
The first challenge I faced was to determine where the player can and can't go. Since I didn't use a physics based collision I needed a way to recognize whether the player is trying to move into a wall or a passable tile
Fortunately Godot tilemaps has a built-in feature that allows you to add custom attributes to each tile. I named each passable tile (e.g. normal, mud etc.) and used a function that returns the type of the tile the player intends to move toward to. The player will only move to the destination tile if it's a passable one.

# Resources

At first I wanted to have 3 resources that players need to watch for: health, energy and time. After some iterating and play testing I realized by adding idle discharging to energy I can mix the two parameters into one, making it for a better user experience.

# Enemies

I designed 4 different enemies for this game, but halfway through I realized that I underestimated the amount of time play testing and iteration requires for a puzzle game. I ended up choosing 2 of them (turrets and mortars) and ditching the other two (drones and laser turrets).


# Power ups & charging stations

To make the game easier and more fair to everyone. I added powerups that would each give you different benefits. Same as enemies I had to cut down all of the powerup except the health powerup


# Packages

To increase replayability and add a little challenge to the game. Each time you pass a level you need to deliver a different package in the same level. Needless to say I had to reduce the amount of packages in here as well.

# Tiles

Tiles play an essential role into designing the level in this game. They don't just act as decoration but they have gameplay mechanics implemented within them. 

# Narratives

Solaris Imperium, once a thriving nation and one of the greatest economic powers, caught in a mysterious situation, unknown forces jamming long-range signals, hacking and controlling defense turrets and drones and turning them against the people, transports are shot down and the only thing that works is something people thought is no longer needed, a courier on foot.

# Concepting & ideation

As a solo dev in Relay rush, I started with concepting and idea iteration, first the game was about a hero in medieval high fantasy that searches dungeons for loots while dodging goblins throwing rocks at them, but eventually, I changed the theme to sci-fi and created C-55.
after some iteration I created some sketch of the gameplay and maps then using Godot, I created prototypes to validate my assumptions.

![Relay rush sketch 1](/images/relay-rush-sketch-1.png)

Once the concept was validated and I settled the technical and artistic aspects of the game, I created the first draft of GDD, My workflow consists of creating multiple modular documents for each section of the game rather than jamming everything into a single document, here's a snapshot of C-55 GDD:

![Relay rush c55 gdd](/images/relay-rush-gdd-1.png)

After writing GDD, I created a project schedule using trello and excel, writing down everything that needed to be done for each level with the respect to priority and dependencies

![Relay rush c55 gdd](/images/relay-rush-plan-schedule-1.png)

# Key Learnings

- Designing mechanics is easier than balancing them.
- Playtesting revealed that fewer, well-polished mechanics created a stronger experience than many unfinished ones.
- Early production estimates should allocate significantly more time for iteration.


