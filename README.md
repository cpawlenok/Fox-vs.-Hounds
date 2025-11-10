Overview

Fox and Hounds ’45 is a strategy game I built to explore search algorithms and adversarial AI design.
The project implements two distinct agents—one for the Fox and one for the Hounds—each using different approaches to decision-making. I used this project to deepen my understanding of pathfinding, the Minimax algorithm, and alpha–beta pruning through simulation and statistical evaluation.

Rules of the Game

The board is a 6×6 grid, rotated diagonally.

Fox: one piece, starts at the top corner and can move up, down, left, or right to any empty dark square. The Fox wins by reaching the opposite corner.

Hounds: four pieces starting near the bottom two rows. Each can move only forward or sideways (never backward). The Hounds win by trapping the Fox so it has no valid moves.

The Fox always moves first. Players alternate turns until one side wins.

No jumps or captures—positioning and movement restrictions drive the strategy.

AI Implementations
Agent	Algorithm	Description
Fox – Random AI	Uniform random	Selects a valid move at random. Serves as a baseline.
Hounds – Random AI	Uniform random	Random movement within legal spaces.
Fox – Shortest Path AI	Dijkstra’s algorithm	Calculates the minimum-distance route to the goal while avoiding Hounds.
Hounds – Minimax AI	Minimax (+ alpha–beta pruning)	Plans several turns ahead (depth ≥ 4) to maximize positional advantage and block the Fox.

Each AI operates independently, allowing full simulation of different matchups.

Architecture

GameBoard class manages:

Board state and move validation

Turn alternation and win detection

Rendering (ASCII or matplotlib visualization)

AI Modules implement move selection strategies.

Simulation Engine runs automated tournaments and logs results.

Implemented in Python 3 / Jupyter Notebook, easily portable to other interfaces (e.g., p5.js).

Evaluation

I ran 100 games per condition across all four combinations:

Random Fox vs Random Hounds

Shortest-Path Fox vs Random Hounds

Random Fox vs Minimax Hounds

Shortest-Path Fox vs Minimax Hounds

Each simulation recorded:

Winner (Fox or Hounds)

Number of turns per game

Overall win percentages

These results were visualized through charts and summary tables to measure AI performance and balance.

Key Learnings

Implementing shortest-path search on a dynamic board environment reinforced graph traversal fundamentals.

Building a depth-limited Minimax with pruning clarified trade-offs between search depth and runtime complexity.

Running large-scale simulations revealed how simple heuristics can outperform random play without full state evaluation.

Possible Extensions

Smarter heuristic functions for Minimax.

GUI or web-based visualization using p5.js.

Variable board sizes and movement rules to explore emergent strategies.

Reinforcement-learning variant that trains agents over repeated matches.

Getting Started

Clone the repo

git clone https://github.com/<your-username>/fox-and-hounds-45.git
cd fox-and-hounds-45


Launch Jupyter Notebook or run the Python script:

jupyter notebook
# or
python fox_and_hounds_45.py


Run simulations and view results.
