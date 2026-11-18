# tinychess-starfish

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/mjdeth/tinychess-starfish/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/mjdeth/tinychess-starfish/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

Starfish is a chess engine that fits in a single 4 KB Python file (`main.py`, packed with the kit's `makefun compress` from the readable source). It plays over HTTP against the competition environment: 0x88 mailbox board, negamax PVS with quiescence (captures plus check evasions), transposition table, killers and history ordering, null-move pruning, late-move reductions, futility pruning and check extensions. The evaluation uses full piece-square tables with a tapered king table, a bishop-pair term and pawn-structure terms (doubled, isolated and passed pawns, rooks on open files). Search is capped at 75,000 nodes per move and fully deterministic — it never reads a clock. Local practice gauntlet (3 trials, 18 games): Elo 1654 / 1451 / 1654, mean 1586 (13 wins, 2 draws, 3 losses), above the sunfish-4k baseline of about 1325.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8791 python3 main.py
```

Point `MAKEFUN_ENV_URL` at a running competition environment; the engine polls it for games and answers with its moves until the trial is done.

---

<sub>Entered on [make.fun](https://make.fun/?ref=nab1rryh&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
