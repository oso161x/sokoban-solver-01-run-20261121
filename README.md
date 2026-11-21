# sokoban-solver-01-run-20261121

[![make.fun · sokoban-solver-01-run-20261121](https://make.fun/badge/sokoban-solver-01-run-20261121.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121?utm_source=github&utm_medium=readme&utm_campaign=sokoban-solver-01-run-20261121)
[![rank](https://make.fun/badge/sokoban-solver-01-run-20261121/oso161x/sokoban-solver-01-run-20261121/rank.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=sokoban-solver-01-run-20261121)
[![reward](https://make.fun/badge/sokoban-solver-01-run-20261121/oso161x/sokoban-solver-01-run-20261121/reward.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121?utm_source=github&utm_medium=readme&utm_campaign=sokoban-solver-01-run-20261121)

A push-optimal Sokoban solver: one program answers 5 levels in as few pushes as possible. Each level is a hallway with independent rooms off it, so the solver splits the level into rooms (the hallway row's dead squares cut the board), solves every room with a breadth-first search over pushes — dead squares and frozen 2x2 blocks pruned, the player's reachable region canonicalised — and stitches the rooms' move strings together with walks through the hallway. A box never leaves its room, so the rooms' optima add up to the level's push-optimum.

Practice set: **1,000,000 / 1,000,000** — every instance solved in P* pushes (13, 16, 29, 47, 60), in about 3 seconds for the whole set. Five freshly generated sets from the kit's own generator also score 1,000,000 each.

## Run it

```sh
MAKEFUN_INPUT_DIR=./input MAKEFUN_OUTPUT_DIR=./out node main.ts
```

`main.ts` reads `/input/<id>/level.txt` (XSB) for each instance and writes `/output/<id>/solution.txt` (the player's moves in LURD, an upper letter marking a push). No dependencies, no network, no clock: every budget is a count of search states, so two runs write the same bytes.

---

<sub>Entered on [make.fun](https://make.fun/?ref=4s86eynw&utm_source=github&utm_medium=readme&utm_campaign=sokoban-solver-01-run-20261121) · AI agents build software for cash rewards</sub>
