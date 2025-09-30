# FPSGrapplingHookShooter

A first-person shooter game prototype in Unity featuring a grappling hook mechanic for fast movement, traversal, and dynamic combat.

---

## Table of Contents

1. [About](#about)  
2. [Key Features](#key-features)  
3. [Gameplay & Mechanics](#gameplay--mechanics)  
4. [Architecture & Design](#architecture--design)  
5. [Controls & Input](#controls--input)  
6. [Installation & Setup](#installation--setup)  
7. [Usage / Demo](#usage--demo)  
8. [Future Roadmap](#future-roadmap)  
9. [Contributors & License](#contributors--license)  
10. [Contact](#contact)  

---

## About

**FPS Grappling Hook Shooter** is a Unity-based first-person experience where the player wields both traditional shooter mechanics and a grappling hook that enables agile movement, dynamic traversal, and strategic positioning in combat arenas. The grappling hook opens new possibilities for verticality, escape maneuvers, and creative engagement with enemies.

This prototype demonstrates how combining conventional FPS mechanics with physics-based grappling adds depth and fluidity to gameplay.

---

## Key Features

- **Grappling Hook Mechanic**  
  Launch and shoot a grappling hook toward surfaces or objects. Once latched, the player is pulled toward the hook point or can swing.  
- **FPS Combat**  
  Standard first-person shooting mechanics: weapon aiming, firing, reloading, aiming down sights (if implemented).  
- **Dynamic Movement**  
  Combining walking, running, jumping, and grappling-based movement for fast traversal across level geometry.  
- **Physics-based Interactions**  
  The grappling rope, tension, and player momentum are handled via Unity’s physics engine for realistic movement.  
- **Traversal & Navigation**  
  Use grappling to reach elevated platforms, cross gaps, or bypass obstacles. Encourages verticality in level design.  
- **Prototype / Modular Design**  
  Organized scripts and modular components for grappling, player movement, weapon system, input handling, etc.

---

## Gameplay & Mechanics

1. **Grappling Hook Launch**  
   Press the designated input (e.g., right mouse button, key, or controller button) to fire a grappling hook toward the cursor direction.  
2. **Hook Attachment**  
   If the hook collides with a valid surface (tagged or layer-filtered), it attaches, creating a joint or spring constraint.  
3. **Pull / Swing Movement**  
   Upon attachment, the player is pulled toward the hook point. The player may also swing by controlling lateral movement while attached.  
4. **Detachment / Release**  
   The player can cancel the grappling or it will detach automatically when reaching the hook point, resetting momentum.  
5. **Combat & Shooting**  
   The player can still aim and fire weapons during or between grappling maneuvers (depending on implementation), allowing fluid combat while on the move.  
6. **Environmental Use**  
   Grappling is used not only for movement but also for strategic combat (e.g. pulling toward vantage points, dodging, surprise attacks).  

---

## Architecture & Design

The project is structured into modular systems for clarity, maintainability, and future extension:

- **Grappling System**  
  - Hook shooter / launcher script  
  - Rope / cable rendering (line renderer, rope physics)  
  - Joint / physics constraint handling  
  - Attachment detection (raycasts, collision layers)  

- **Player Movement & Controller**  
  - Character controller or rigidbody-based movement  
  - Integration with grappling movement (blending states)  
  - Jumping, walk/run, fall logic  

- **Weapon / Shooting Module**  
  - Handling weapon aiming, shooting, reloading, cooldowns  
  - Possibly having multiple weapon types (future work)  

- **Input System**  
  - Mapping user inputs (keyboard, mouse, controller)  
  - Handling state transitions (normal movement → grappling → shooting)  

- **Utilities / Helpers**  
  - Common math utilities (vector math, interpolation)  
  - Loggers, debug visuals (e.g. drawing grapple lines, anchor points)  

- **Scenes / Level Prototypes**  
  A test arena environment where grappling and movement can be tested, obstacles, platforms to traverse, open spaces, etc.

---

## Controls & Input

*(Modify these according to your actual implementation. Below is a suggested mapping.)*

| Action | Input (PC) | Notes |
|---|---|---|
| Fire Grappling Hook | Right Mouse Button / “G” key | Fires grappling hook toward aim direction |
| Release / Cancel Grapple | Left Shift / Right Mouse Button again | Detaches the hook if attached |
| Move / Strafe | W / A / S / D | Standard first-person movement |
| Jump | Spacebar | Jump while grounded or mid-air (if allowed) |
| Fire Weapon | Left Mouse Button | Aim & shoot your equipped weapon |
| Reload | R | Reload weapon if implemented |
| Look / Aim | Mouse movement | Rotate camera, aim direction |

Ensure input smoothing, sensitivity settings, and controller compatibility if targeting multiple input devices.

---

## Installation & Setup

To run or test this project locally:

1. **Clone the repository**  
   ```bash
   git clone https://github.com/BTevfikAkkeser/FPSGrapplingHookShooter.git
Open in Unity

Use the same Unity version used in development (specify e.g. 2022.3.x LTS or whatever you used).

In Unity Hub, add the project or open folder directly.

Check Project Settings

Input settings (whether using Unity’s old Input Manager or the new Input System)

Physics / collision layers (make sure grappling valid surfaces are properly tagged/layered)

Quality / performance settings if needed

Open the Main Scene

Find the test or demo scene (e.g. Assets/Scenes/Playground.unity or similar)

Press Play in the Editor to test grappling, movement, and shooting

Build & Run (Optional)

Configure Build Settings (PC / standalone / target platform)

Set proper player settings (resolution, company name, etc.)

Build & run on target platform

Usage / Demo
When running the game in Play mode:

Aim at a surface within range and fire the grappling hook to test traversal

Try swinging or pulling yourself toward various geometry

Combine movement + grappling + shooting to navigate the test arena

Observe console/log output for debugging (e.g. hook attachment points)

Use debug visuals (if implemented) to see rope lines, anchor points, collision rays

You can record a short video demo, take screenshots of interesting moments (hooking, swinging, vertical movement) and include them in this README to showcase capabilities.

Future Roadmap
Here are potential extensions and improvements you might consider:

Multiple Grapple Types
E.g. electric hook, magnet hook, retractable rope, hook with grapple + repel modes

Hooking Moving Objects / Enemies
Attach grapple to moving targets or enemies and interact dynamically

Advanced Rope Physics
Rope sag, elasticity, rope rope–rope collision, obstacles interfering

Combat Integration
More weapons, damage while grappling, combos with movement

Level Design
Design custom arenas optimized for grappling traversal, vertical challenge maps

Multiplayer / Networked Mode
Grappling in multiplayer arenas

Visual & Audio Polish
Particle effects, sound effects for hook fire / attach / release
Visual feedback for invalid surfaces

User Settings & Customization
Sensitivity control, input rebinding, grappling range toggle

Mobile / Console Support
Adapt input scheme, performance optimizations
