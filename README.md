# tiny-chess-01 — 4 KB chess engine

A compact, deterministic chess engine in Python: 0x88 board, negamax with
alpha-beta + transposition table + quiescence search, tapered piece-square
evaluation, check extensions, mate-distance pruning, a fixed 90,000-node
budget per move (never clock-based), and a 15-position opening book keyed by
position hash.

## Files

- `engine.py` — readable source. The competition entrypoint `main.py` is
  produced from it with the kit's compress command:
  `node cli/makefun.mjs compress engine.py --out main.py`
  (simulated packed size ~3,730 bytes, under the 4,096 limit).
- `LICENSE` — MIT.

## Running

- Local / test mode (no env): feed FEN positions on stdin, one per line;
  the engine prints the best move in UCI on stdout.
- Trial mode: set `MAKEFUN_ENV_URL` and the engine polls the env for the
  game in play and posts its moves in UCI.
