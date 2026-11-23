# Flag Rush

A 2D top-down maze game made in Godot 4.3. Collect as many flags as you can while three enemies chase you through the maze.

## How to play

- Move with **WASD** or the **arrow keys**.
- Touch the flag to score a point. A new flag then appears at a random spot in the maze.
- Avoid the enemies. If one catches you, the run ends and you go back to the start screen, which shows your last score and your high score.

## How it works

- **Enemy AI:** each enemy uses Godot's `NavigationAgent2D` to pathfind through the maze toward the player. The three enemies start in different parts of the map and move at different speeds.
- **Flag spawning:** spawn points are placed as `Marker2D` nodes, and the level picks one at random each time a flag is collected.
- **Signals:** the flag and the enemies emit signals (`point` and `hit`) that the level script handles to update the score or end the run.
- **Shared state:** a global autoload script (`variables.gd`) keeps track of the player's position, the current score and the high score across scenes.
- **Collision layers:** separate physics layers for the player, enemies, walls and objectives.

## Running it

1. Install [Godot 4.3](https://godotengine.org/) or later.
2. Clone the repo: `git clone https://github.com/jackluehrs/Flag-Rush.git`
3. In Godot, click **Import** and select `project.godot`.
4. Press **F5** to play.

## Project structure

| File | Purpose |
| --- | --- |
| `level.gd` | Main game scene: score, flag spawning, game over |
| `player.gd` | Player movement |
| `enemies.gd` | Enemy pathfinding and collision |
| `flag.gd` | Flag pickup and repositioning |
| `hud.gd` | Start screen with previous score and high score |
| `variables.gd` | Global state shared between scenes |
| `Art/` | Sprites and tile art |

## Credits

Made with a partner (original repo: [luehrsan/JD-First-Game](https://github.com/luehrsan/JD-First-Game)). I programmed the core gameplay in GDScript and created the art.
