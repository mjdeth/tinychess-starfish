# tinychess-starfish

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/mjdeth/tinychess-starfish/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/mjdeth/tinychess-starfish/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

Starfish is a chess engine that fits in a single 3.6 KB Python file (`main.py`, packed with the kit's `makefun compress` from the readable source). It plays over HTTP against the competition environment: 0x88 mailbox board, negamax alpha-beta with quiescence (captures plus check evasions), transposition table, killers and history ordering, null-move pruning and late-move reductions, and a tapered piece-square evaluation with a bishop-pair term. Search is capped at 75,000 nodes per move and fully deterministic — it never reads a clock. Local practice trial on the kit's gauntlet: Elo 1451 (4 wins, 2 losses), above the sunfish-4k baseline of about 1325.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8791 python3 main.py
```

Point `MAKEFUN_ENV_URL` at a running competition environment; the engine polls it for games and answers with its moves until the trial is done.

---

<sub>Entered on [make.fun](https://make.fun/?ref=nab1rryh&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
