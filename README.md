# tiny chess

A tiny Python chess engine under 4KB. It reads FEN from stdin, searches with alpha-beta, and prints a move.

## usage

Feed a FEN line on stdin and read the chosen move back. The engine keeps the interface small: one position in, one move out.

## engine

Search uses alpha-beta with a transposition table, quiescence for captures, and piece-square tables for placement. Movegen builds legal moves, nodes count the work, and mate lines end the search early.

## testing

Perft checks movegen counts. Mate positions check finishing lines. Small positions check that search, tables, and quiescence agree.

## limits

Tiny means limits: 4KB of code, shallow depth on busy positions, and simple evaluation. It plays chess, it does not promise mastery.
