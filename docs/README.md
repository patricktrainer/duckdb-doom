# DuckDB-DOOM Documentation

This directory contains documentation and media for the DuckDB-DOOM project.

## Contents

- `screenshot.png` - Screenshot of the game in action

## Game Architecture

### Database Schema

The game uses the following tables:

1. `map` - Stores the level layout with wall and floor tiles
2. `player` - Single row table with player's position and direction
3. `enemies` - Stores enemy positions and states
4. `bullets` - Tracks projectiles in the game world
5. `settings` - Game configuration parameters

### Views

1. `render_3d_frame` - Recursive CTE that implements raycasting for the 3D view
2. `column_distances` - Stores depth information for the Z-buffer

### Game Loop

The game loop consists of:

1. Processing input (WASD keys, spacebar)
2. Updating game state (moving bullets, checking collisions)
3. Rendering the 3D view and minimap

### Rendering Technique

The 3D rendering uses raycasting, similar to early 3D games like Wolfenstein 3D:

1. Cast rays from the player position
2. Calculate distance to walls
3. Draw vertical lines with height based on distance (closer walls appear taller)
4. Add simple shading based on distance
5. Overlay entities (enemies, bullets) at the correct depth

## Performance Considerations

The game uses SQL for all logic, which is not optimized for real-time rendering. Some optimizations include:

1. Limiting the view distance
2. Using a modest resolution
3. Caching database connections
4. Careful use of recursive CTEs
