# FlatPhysics

A small 2D rigid-body physics engine in C++, with a slingshot game prototype built on it using raylib.

Hobby project from 2023, written with two other contributors.

The engine supports circles, boxes, convex polygons and triangulated concave shapes, with
AABB broad phase, SAT collision detection and impulse-based resolution (rotation and friction).
The `game` branch (default) holds the slingshot prototype; `master` holds the earlier engine demo.

## Requirements

- Windows, Visual Studio 2022 with "Desktop development with C++" (toolset v143)
- raylib 4.2, bundled as 32-bit headers and libraries in `include/` and `lib/`

## Run

1. Open `FlatPhysics.sln`.
2. Select the `Debug` / `x86` configuration and run (F5).

The game loads textures from `asset/`, so it must start with `FlatPhysics/` as the working
directory (the Visual Studio default).

## Controls

- Click on the title screen to start
- Drag and release the projectile with the left mouse button to launch it
- Mouse wheel: zoom, arrow keys: pan the camera, `T`: reset the camera
- `||` button: pause menu (`Resume`, `Retry`, `Mainmenu`; `Retry` resumes without resetting the scene)
- `C` / `G`: jump to the game-clear / game-over screen. These debug shortcuts are the only way
  to reach either screen; the HP bar and remaining-shot counter are drawn but never change.

## Structure

- `FlatPhysics/src/Engine/PhysicsEngine/` - bodies, collision, world step
- `FlatPhysics/src/Engine/GameEngine/` - raylib drawing helpers and UI buttons
- `FlatPhysics/src/Game/` - entry point (`Application.cpp`) and game logic
