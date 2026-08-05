---
title: "Dust devil"
permalink: /personal-projects/devil-dust
author_profile: true
---
<video width="720" height="480" controls>
  <source src="/images/dust-devil-trailer.mp4" type="video/mp4">
</video>

**Genre:** Twin stick shooter, arcade, adventure, 3D  
**Team size:** 2  
**Duration:** 1 week ( for stop killing game community jam)  
**Release date:** July 2026  
**Platforms:** Web browser/Windows  
**Roels:** Game designer, Level designer, Programmer  
**Tools:** Godot 4, Microsoft office, Google suite, Trello  
**Play:** [Browser/Windows](https://aethewn.itch.io/dust-devil)  
**Description:** Dust Devil is a 3D arcade twin-stick shooter inspired by science-fiction desert settings such as Dune and classic arcade action games. Players explore a hostile desert, engage enemy patrols, and survive increasingly dangerous encounters while maintaining momentum across large sand dunes.

# Responsibilities

---

My contributions included:

* Designing vehicle navigation system.
* Designing infantry and enemy vehicle behaviors.
* Designing combat encounters.
* Designing UI/UX elements.
* Designing the desert level.
* Creating and maintaining the Game Design Document.
* Programming gameplay systems.

# Vehicle navigation system

---

### Design Goals

Since the game is built around driving across large desert dunes, movement quality directly affected the entire player experience. A vehicle that felt too heavy would make combat frustrating, while a vehicle that was too loose would reduce player control.

The goal was to create a vehicle that:

* Responded quickly to player input.
* Smooth drifting without sacrificing control.
* Made jumping over dunes feel rewarding and satisfying.
* Supported fast arcade style gameplay.

### Root cause analysis

Given the project's limited schedule, creating a vehicle physics system from scratch was impractical so I evaluated couple of freely available vehicle physics solutions and selected the Easy Vehicle Physics plugin as a starting point. Although the plugin provided functional vehicle behavior, its default tuning emphasized realistic handling.

During playtesting I identified several issues:

Steering felt delayed.
Vehicles carried excessive momentum.
Drifting was difficult to control.
Jumping over dunes lacked excitement.

While the underlying system was technically solid, it did not support the fast-paced arcade experience we wanted.

### Exploring solutions

Rather than replacing the physics system, I treated the plugin as a configurable framework and focused on redesigning its handling characteristics.

To establish clear design targets, I analyzed arcade driving games such as PAKO 2, focusing on:

Steering responsiveness.
Drift forgiveness.
Momentum management.
Airborne control.

![vehicle navigation balance editor](/images/dust-devil/vehicle-navigation-system-balance-editor.png)

### Designing and balancing new navigation system

Using these observations, I iteratively adjusted numerous handling parameters until the vehicle consistently delivered the intended player experience.

![vehicle navigation balance spreadsheet](/images/dust-devil/vehicle-navigation-system-balance-spreadsheet.png)

Additional effects were added to improve player feedback:

* Tire trail shaders were implemented to leave visible marks across the dunes.
* Visual feedback helped reinforce the feeling of speed and interaction with the environment.

### Results

The redesigned handling successfully shifted the experience from simulation-oriented driving to responsive arcade gameplay.

Players could quickly change direction, drift confidently through encounters, and use dunes as opportunities for expressive movement rather than obstacles.

Although built on an existing physics framework, careful tuning transformed the system into one that supported the intended gameplay experience.

# Infantry Units

---

### Design goals

Infantry units were designed to create persistent environmental pressure during exploration.

Rather than acting as individually complex opponents, they served as area-control enemies that encouraged movement and prevented long periods of safe traversal.

Design objectives included:

* Simple, readable behavior.
* Low implementation cost suitable for a game jam.
* Continuous pressure on the player.
* High encounter density.

### Root cause analysis

Early implementations used over 200 individual 3D infantry units.

While this achieved the desired battlefield density, performance quickly became a major issue.

This presented an important design trade-off:

Maintain the visual scale of encounters while reducing computational cost.

### Exploring solutions

I approached the problem through multiple iterations.

First, I removed unnecessary character models to reduce rendering cost.

Although this improved performance, it was insufficient.

Next, I implemented object pooling to eliminate frequent object creation and destruction during gameplay.

Finally, I redesigned encounter composition by organizing infantry into patrol groups rather than treating every unit as an independent encounter.

This reduced the total number of active enemies while preserving the player's perception of a populated battlefield.

### Designing infantry units

Infantry behavior was intentionally straightforward.

Each squad followed a simple gameplay loop:

* Patrol a designated area.
* Detect nearby players.
* Pursue the player.
* Attack while within range.
* Return to patrol after losing the target.

A lightweight state machine controlled these behaviors, allowing enemy logic to remain predictable, easy to balance, and quick to iterate during development.

An infantry manager handled pooled spawning and squad management.

![enemy-ai-flowchart](/images/dust-devil/enemy-ai-flowchart.png)

### Implementation

To keep enemy behavior predictable while remaining extensible, I designed a simple state machine with Patrol, Chase, Attack and Return states. This made enemy behavior easier to tune and allowed rapid iteration during the jam.

### Results

Grouping enemies and pooling instances significantly improved runtime performance while maintaining combat intensity.

The final design provided continuous pressure throughout exploration without overwhelming either the player or the hardware.

# Enemy Vehicles

---

### Design goals

While infantry controlled space, enemy vehicles were designed to create dynamic pursuit encounters.

Their purpose was to interrupt exploration and force players into high-speed combat situations that contrasted with stationary infantry encounters.

The intended gameplay experience was:

* Increased tension.
* Mobile threats.
* Continuous movement during combat.
* Greater encounter variety.

### Root cause analysis

Initially, I explored creating a custom vehicle system for enemy AI. However, given the remaining development time, this approach carried unnecessary risk. Instead, I reused the tuned player vehicle system and adapted it for AI-controlled enemies but they didn't feel dynamic or a big challenge to the player. The problem was that the enemy cars can only chase and crash into the player and lack any ability to shoot at the player.

### Exploring solutions

I evaluated two possible weapon behaviors: high fire rate with low damage, and low fire rate with high damage. Due to the limited scope of the game jam, I selected the first option, as it required less balancing effort while still creating consistent pressure on the player.

### Designing enemy vehicle

Their behavior:

* Remain inactive until the player enters their detection range.
* Chase the player across the desert.
* Continue pursuit until either the player or enemy vehicle is destroyed.

The combination of stationary infantry threats and mobile vehicle threats created different combat situations without requiring complex AI systems.

Through iterations I found the optimal detection range and chasing range, at first it was too short so the infantry wouldn't follow the player as long as we wanted but by balnacing that, this issue was solved.

### Implementation

I used the state machine I made for the infantry units and similar to infantries I created a car manager system where it would spawn the cars from a pool.


### Results

Combining stationary infantry with mobile vehicle patrols created encounters with distinct pacing and decision-making.

Players were required to balance positioning, movement, and target prioritization instead of responding to a single enemy type.

This increased encounter variety while keeping AI complexity relatively low.

# Key Takeaways

---

Dust Devil reinforced the importance of player feel in action games.

Through this project, I learned that small details such as vehicle responsiveness, visual feedback, and movement effects can significantly impact player enjoyment (and the cat model because everyone was mentioning it).

Working within the game jam environment also improved my ability to prioritize features, communicate design decisions, and focus development effort on the elements that create the strongest player experience.