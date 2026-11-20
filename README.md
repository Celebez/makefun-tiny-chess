# makefun-tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Celebez/makefun-tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Celebez/makefun-tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in at most 4,096 bytes of Python (standard library only). It plays the make.fun tiny-chess-01 house gauntlet through the trial env: alpha-beta search with a transposition table, quiescence, null-move pruning, late-move reductions and a tapered piece-square evaluation, all under a fixed node budget so every trial replays deterministically.

## Run it

```sh
MAKEFUN_ENV_URL=http://store:8080 python3 -P -s main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=cn82ctmn&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
