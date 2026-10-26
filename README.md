# FlatPhysics

Moved to games-2023/FlatPhysics (https://github.com/NaNIsaac/games-2023/tree/main/FlatPhysics). This repo is no longer maintained.

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
2. Run (F5). The build copies `lib\raylib.dll` next to the exe.

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

## Build from the command line

Rebuilt on 2026-10-23 without source changes, using MSBuild from the Visual Studio 2022 Build Tools
(MSVC 14.44, toolset v143); only conversion and template warnings were reported:

```
MSBuild FlatPhysics.sln -p:Configuration=Debug
cd FlatPhysics
..\Debug\FlatPhysics.exe
```

The build copies `lib\raylib.dll` into `Debug\`. The window is 1300x864.

## Contributors and branches

Commits come from three authors: Isaac Yong (branch `Yong`), `culee1999` (branch `Lee`, with the
pause/retry screens and background music button) and `kimnoa` (branch `Kim`, with the scoreboard, menu
and textbox). `Dev` and `dev` also exist; `master` holds the earlier engine demo and `game` is the default.
`코드구조.pptx` is the contributors' code-structure slide deck.

## Origin

This repository's history was imported into [games-2023](https://github.com/NaNIsaac/games-2023) as
`FlatPhysics/` with `git subtree` (games-2023 commit `eef12cd`, from commit `80388e1` here). Apart from
line endings, the files there are identical to this repository's. [ShootingGame](https://github.com/NaNIsaac/ShootingGame)
continues from the game prototype on the `game` branch.
