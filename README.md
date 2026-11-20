# makefun-tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Celebez/makefun-tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Celebez/makefun-tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in at most 4,096 bytes of Python (standard library only). It plays the make.fun tiny-chess-01 house gauntlet through the trial env: alpha-beta search with a transposition table, quiescence, null-move pruning, late-move reductions and a tapered piece-square evaluation, all under a fixed node budget so every trial replays deterministically.

## Implementation and validation

`main.py` contains the entire engine as a Latin-1 LZMA payload, produced with the kit's `makefun compress`. It decompresses into memory; it does not load another repository file or call a model. The readable authoring source and native agent sessions accompany the private submission bundle.

The legal-move core passes the standard start, Kiwipete and positions 3–6 perft checks, including castling, en passant and underpromotion. Before search tuning, the compact build matched the original's legal moves and evaluation on 270 positions, and its chosen move and node count on 100 fixed-budget searches. A regression test verifies that transposition-table moves precede captures. The search uses a fixed budget of 100,000 nodes per move. It gets a new transposition table on each move: keeping the table between moves lost to two opponents the fresh-table build beat in local practice. Fixed hash seeds and stable ordering make decisions independent of wall time.

## Run it

```sh
MAKEFUN_ENV_URL=http://store:8080 python3 -P -s main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=cn82ctmn&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
