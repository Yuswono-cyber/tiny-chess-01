# tiny-chess-01 entry — 4 KB Python chess engine

`main.py` is the whole engine (4,044 bytes): a compressed payload that
unpacks to a 0x88-board negamax search with alpha-beta + PVS, a
transposition table, quiescence search with in-check evasions, killer-move
ordering and MVV-LVA, and tapered piece-square evaluation (Michniewski
tables, dual king tables, bishop pair). It searches to a fixed node cap
(100,000 nodes per move) — never to a clock — so replays match exactly.

It plays the gauntlet through the env at `MAKEFUN_ENV_URL`:
`POST /game` serves the game in play, `POST /move` plays a move in UCI.
No other file is read or imported; Python 3.13 standard library only.
