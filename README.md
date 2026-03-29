# ♟️ chess-ai-arena

A from-scratch Python chess engine where classical and probabilistic AI algorithms compete head-to-head — with every matchup benchmarked and logged.

Built originally as a college project, extended into a passion project driven by one question: *which search strategy actually wins, and why?*

## 🧠 Algorithms Implemented

### Minimax Family
- **Standard Minimax** with alpha-beta pruning
- **Beam Search** — pruned branching for speed
- **Iterative Deepening** — depth-first with time awareness

### MCTS Family
- **Standard MCTS** — simulation-based decision making
- **Progressive History MCTS** — move history-weighted selection
- **RAVE MCTS** — rapid action value estimation

### Baseline
- **RandomAgent** — uniform random legal move selection

### Key Components:
---------------------
#### ♔ ChessPiece:
♕ Piece identity + legal move generation per type.

#### ♔ ChessBoard:
♕ Board state, move validation, attack tracking, checkmate detection.

#### ♔ MinimaxAgent:
♕ Minimax variants (standard, beam search, iterative deepening)

#### ♔ MCTS:
♕ MCTS variants (standard, progressive history, RAVE).

#### ♔ RandomAgent:
♕ Random legal move selection (baseline).

#### ♔ ChessGame:
♕ Orchestrates agents + board, visualizes play, logs results

All classes are modular — any two agents can be dropped in as players.

## 📊 Benchmark Results

All 15 head-to-head matchups run to completion.

Key findings:
=============
|        White        |         Black       |       Result         |Moves|
|---------------------|---------------------|----------------------|-----|
| Standard Minimax    | Beam Search         | **Checkmate**        | 39  |
| Standard Minimax    | Iterative Deepening | Draw                 | 50  |
| Standard Minimax    | Standard MCTS       | Draw                 | 50  |
| Standard Minimax    | Progressive MCTS    | **Checkmate**        | 7   |
| Standard Minimax    | RAVE MCTS           | **Checkmate**        | 39  |
| Beam Search         | Iterative Deepening | Draw                 | 50  |
| Beam Search         | Standard MCTS       | Draw                 | 50  |
| Beam Search         | Progressive MCTS    | Draw                 | 50  |
| Beam Search         | RAVE MCTS           | Draw                 | 50  |
| Iterative Deepening | Standard MCTS       | **Checkmate**        | 23  |
| Iterative Deepening | Progressive MCTS    | **Checkmate**        | 31  |
| Iterative Deepening | RAVE MCTS           | **Checkmate**        | 35  |
| Standard MCTS       | Progressive MCTS    | Draw                 | 50  |
| Standard MCTS       | RAVE MCTS           | Draw                 | 50  |
| Progressive MCTS    | RAVE MCTS           | Draw                 | 50  |

**Notable observations:**
- Iterative Deepening is the strongest overall performer — beats all MCTS variants
- Beam Search is the fastest (avg 0.17–0.27s/move) but draws frequently
- Progressive MCTS beat Standard Minimax in just 7 moves — fastest checkmate recorded
- MCTS variants largely draw among themselves, suggesting similar search quality
Average move times - White: 1.04s, Black: 1.04s

All CHECKMATES in the game!!
----------------------------
![image](https://github.com/user-attachments/assets/67c35abe-5ba8-4f6d-a3e4-04cc165f1c33)
![image](https://github.com/user-attachments/assets/d7b97122-0730-484b-988b-83751268d394)
![image](https://github.com/user-attachments/assets/3e3f9fe2-3e34-4fa4-a7be-de49128a73e0)
![image](https://github.com/user-attachments/assets/5558e853-4137-434d-ae77-a4b1a46fea37)
![image](https://github.com/user-attachments/assets/acbee8e8-5546-4dfd-b321-9c89b43eb5f1)
![image](https://github.com/user-attachments/assets/f1ffa3bf-ddd0-4569-b5f6-4995161eb61a)

## 🚀 Getting Started

**Requirements:** Python 3.x — no external dependencies
```bash
git clone https://github.com/Hamsini11/chess-ai-arena.git
cd chess-ai-arena
python main.py
```

This runs all agent matchups sequentially, visualizes each game on the console, 
and prints summary stats at the end.

**To adjust game length:**
```python
# In ChessGame class
game = ChessGame(max_moves=50)  # increase or decrease as needed
```

**Console tip:** To see full output without truncation:
`File → Preferences → Settings → search "scrollback" → set to 1000 or higher`


## 🔮 Future Directions

- Neural network evaluation function (replacing hand-crafted heuristics)
- Opening book integration
- GUI with move-by-move replay
- Elo rating system across extended tournament runs


## 📄 License

GNU-3.0 — use it, extend it, keep it open.


*Built by [Hamsini A Kumar](https://www.linkedin.com/in/hamsini-a-kumar)*
