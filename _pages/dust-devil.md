---
title: "Devil dust"
permalink: /personal-projects/devil-dust
author_profile: true
---
---
##### Genre: Twin stick shooter, arcade, adventure, 3D
##### Team size: 2
##### Duration: 1 week ( for stop killing game community jam)
##### Released:  2026
##### Platforms: Web browser/Windows
##### My role: Game designer, Level designer, Programmer
##### Tools: Godot, Microsoft office, Google suite, Trello
##### Play: **[Browser/Windows](https://aethewn.itch.io/dust-devil)**
---
# Overview
---
<video width="720" height="480" controls>
  <source src="/images/dust-devil-trailer.mp4" type="video/mp4">
</video>
Dust Devil is a 3D twin-stick shooter inspired by desert science-fiction worlds such as *Dune* and classic retro arcade shooters.

The goal of the project was to create a simple-to-learn but challenging arcade experience where players could immediately understand the controls while still having opportunities to improve their performance through movement, positioning, and combat decisions.

Because the project was created within a one-week game jam, the design focus was on creating a strong core gameplay loop rather than building a large amount of content.

The final gameplay loop became:  
**Explore the desert → engage enemies → survive encounters → achieve a higher score**

# Design Goals
---
The main design goals were:

* Create responsive vehicle movement that feels enjoyable to control.
* Combine fast-paced shooting with movement-based challenges.
* Build a recognizable desert environment with a retro arcade feeling.
* Create enemy encounters that are easy to understand but require player awareness.


<video width="720" height="480" controls>
  <source src="/images/dust-devil-trailer.mp4" type="video/mp4">
</video>

# Responsibilities
---

My contributions included:

* Designing core gameplay mechanics.
* Designing and balancing the level layout.
* Creating and maintaining the Game Design Document.
* Programming gameplay systems.
* Implementing and adjusting vehicle movement.
* Designing UI/UX elements.

# Player Vehicle Design

## Challenge

The biggest design challenge was creating vehicle movement that felt satisfying.

Since the game is built around driving across large desert dunes, movement quality directly affected the entire player experience. A vehicle that felt too heavy would make combat frustrating, while a vehicle that was too loose would reduce player control.

The goal was to create a vehicle that:

* Responded quickly to player input.
* Felt fun when drifting across the terrain.
* Made jumping over dunes feel rewarding.
* Supported fast arcade-style gameplay.

## Implementation

Due to the one-week development timeline, we used a Godot vehicle plugin as a foundation and modified it to fit our gameplay needs.

I adjusted the vehicle behavior to better match an arcade experience rather than a realistic driving simulation.

Additional effects were added to improve player feedback:

* Tire trail shaders were implemented to leave visible marks across the dunes.
* Visual feedback helped reinforce the feeling of speed and interaction with the environment.

These changes improved the connection between player input and the game world, making movement feel more impactful.

---

# Level Design

## Goal

My goal for the level was to create a retro-inspired desert battlefield surrounded by mountains, providing a clear gameplay space while maintaining the feeling of exploration.

The environment needed to support:

* Vehicle traversal.
* Enemy encounters.
* Open movement opportunities.
* Visual identity.

## Process

The terrain was created using the Terrain3D plugin with a dune-based preset.

Because of the limited jam timeline, I focused on efficient encounter placement instead of building a highly scripted level.

Enemies were distributed across the map in groups, allowing easier balancing and creating natural combat zones.

This approach helped create variety in gameplay while keeping development manageable within the one-week deadline.

---

# Enemy Design

## Enemy Types

The original design included two enemy categories:

1. Infantry Units
2. Enemy Vehicles

## Infantry Units

Infantry enemies were designed around proximity-based behavior.

Their intended behavior:

* Patrol designated areas.
* Detect the player when they enter a certain range.
* Follow the player.
* Attack until the player escapes their detection range.

This created pressure during exploration while keeping the behavior simple enough for a short development cycle.

## Enemy Vehicles

Enemy vehicles were designed to create higher-intensity encounters.

Their behavior:

* Remain inactive until the player enters their detection range.
* Chase the player across the desert.
* Continue pursuit until either the player or enemy vehicle is destroyed.

The combination of stationary infantry threats and mobile vehicle threats created different combat situations without requiring complex AI systems.

---

# Development Constraints & Solutions

## Constraint: One-Week Development Timeline

The biggest production challenge was balancing ambition with available time.

To stay within scope, we prioritized:

* A strong movement system.
* A clear gameplay loop.
* Simple but readable enemy behaviors.
* A focused environment.

Instead of creating many mechanics, we concentrated on making the core driving and shooting experience enjoyable.

## Result

Dust Devil successfully delivered a compact arcade experience built around movement, combat, and survival.

The project helped me develop practical experience in:

* Designing mechanics under strict constraints.
* Iterating on player controls.
* Balancing gameplay systems quickly.
* Collaborating across design and programming responsibilities.

---

# Key Takeaways

Dust Devil reinforced the importance of player feel in action games.

Through this project, I learned that small details such as vehicle responsiveness, visual feedback, and movement effects can significantly impact player enjoyment.

Working within a one-week game jam environment also improved my ability to prioritize features, communicate design decisions, and focus development effort on the elements that create the strongest player experience.
