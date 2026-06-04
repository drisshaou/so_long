*This project has been created as part of the 42 curriculum by drhaouha.*

# So Long

## Description

A small 2D game built in C using the MiniLibX graphical library. The player controls a character navigating a tile-based map, collecting all items before reaching the exit via the shortest possible route. The project covers window management, event handling, textures, sprites, and basic map parsing/validation.

## Features

| Feature | Details |
|---------|---------|
| Movement | W/A/S/D or arrow keys (up, down, left, right) |
| Goal | Collect all collectibles (`C`), then reach the exit (`E`) |
| Move counter | Displayed in the shell at every move |
| Map format | `.ber` text file — rectangular, wall-enclosed, path-validated |
| Window | ESC key or click ✕ to close cleanly |

### Map characters

| Char | Meaning |
|------|---------|
| `0` | Empty space |
| `1` | Wall |
| `C` | Collectible |
| `E` | Exit |
| `P` | Player starting position |

A valid map must contain exactly 1 `P`, 1 `E`, and at least 1 `C`, be rectangular, fully enclosed by walls, and have a reachable path from `P` to all `C` and `E`.

## Bonus

- Enemy patrols — touching one causes the player to lose
- Sprite animations
- Move counter displayed on screen (instead of shell only)

## Instructions

### Compilation

```bash
make
```

Requires MiniLibX (either the school's version or compiled from sources).

### Usage

```bash
./so_long maps/your_map.ber
```

### Map example

```
1111111111111
10010000000C1
1000011111001
1P0011E000001
1111111111111
```

### Error handling

Any invalid map (wrong format, missing components, no valid path, non-rectangular, etc.) will cause the program to exit with:

```
Error
<explicit error message>
```

### Makefile rules

```bash
make        # build
make clean  # remove objects
make fclean # remove objects + binary
make re     # fclean + build
make bonus  # build with bonus features
```

## Rules

- C only — written in accordance with the 42 Norm
- No unexpected exits (no segfault, double free, memory leak)
- MiniLibX images mandatory for rendering
- No unnecessary Makefile relinking
- Bonus files in `_bonus.{c/h}` unless stated otherwise

## Resources

- [MiniLibX documentation](https://harm-smits.github.io/42docs/libs/minilibx)
- [MiniLibX — 42 Linux sources](https://github.com/42Paris/minilibx-linux)
- [itch.io — free 2D game assets](https://itch.io/game-assets/free)
- [Flood fill algorithm (path validation)](https://en.wikipedia.org/wiki/Flood_fill)
- [cplusplus.com — C file I/O](https://cplusplus.com/reference/cstdio/)
