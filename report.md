# Project 6 Report: Myanmar Checkers AI Visualizer

> [!IMPORTANT]
> **AUTOGRADER COMPLIANCE INSTRUCTIONS:**
> This report is parsed automatically by the autograder. To ensure you receive full credit for your work:
> 1. **Do not modify** the section headers (`## ...`) or bold field keys (e.g., `**Name:**`, `**Primary AI Algorithm:**`, `**Live Deployment URL:**`, etc.).
> 2. **Write your answers directly after** the colon `:` of each field, replacing the placeholder text completely (including the outer brackets `[` and `]`).
> 3. **Maintain the file structure**. Changing headers, bold titles, or deleting lines can cause the autograder to miss your responses and award 0 marks.

---

## Student Information
- **Name:** Khin Yadanar Aung
- **MMDT ID:** MMDT002

---

## Section 1: AI Agent Configuration
- **Primary AI Algorithm:** Minimax with Alpha-Beta Pruning
- **Pruning Technique:**  Alpha-Beta Pruning
- **Evaluation Heuristic Strategy:**  Piece Advantage, Positional Weights, Weighting on the King

---

## Section 2: Complexity & Evaluation Function Analysis
- **Board Configuration:** 8x8 board, 64element list with 2D render, piece sit only in the dark square, the white are on 0 to 2 and the black are on rows 5 to 7 and they move horizontally,
- **Piece Valuation & Rules:** There are four piece black, white, king black, king white. The get_available_move  capture of opponent and their move while make move did the move of the piece. The undo move support to the minmax search to look ahead.
- **Heuristic Features Used:** Calculate how many pieces and kings each side has. More weight on king as it could freely move diagonally on the board. (my_pieces - opp_pieces) + 3x(my_kings - opp_kings)
 + 0.1 x (my_chance - opp_chance)
---

## Section 3: Local Verification & Feature Checklist
*Check the algorithms, agents, and features you successfully ran and verified on your local development server by placing an `x` in the brackets (e.g., `[x]`):*
- [x] Myanmar Checkers Game Engine & Board State Representation
- [x] Legal Move Generation and Capture Mechanics
- [x] Minimax Search Algorithm with Alpha-Beta Pruning
- [x] Rule-Based / Heuristic AI Agent
- [x] Uniform Random Baseline Agent
- [x] Interactive Web Visualizer with Playable Board & Game Feedback

---

## Section 4: Deployed and Presentation Information
- **Deployment Platform:**  Render
- **Live Deployment URL:** https://checker-mmdt002.onrender.com
- **Video Presentation Link:** [Provide an accessible link to your 5–7 minute video presentation]

---

## Section 5: Discussion
*Provide your written analysis for each point by replacing the bracket placeholders below:*
- **Explain how Alpha-Beta pruning optimizes decision-making in large-branching board games like Checkers without sacrificing tactical depth.**
The Alpha-Beta pruning improve the algorithm by eliminating the moves that dont affect the final decision.The alpha tries to get the highest possible scores for min while the beta tries to get the lowest possible score for max. For example, in checker, if the opponent (MIN) can choose between two moves with scores of +2 and +5, they will choose +2 because it gives MAX a lower score. Therefore, Beta becomes +2. If Alpha is already +5 from a previously explored move, then Alpha ≥ Beta (+5 ≥ +2), so Alpha-Beta pruning can stop exploring the remaining branches because MAX will not choose this option.  
- **Compare classical Adversarial Search & Heuristic Evaluation in Checkers with modern Generative AI / Deep Reinforcement Learning game agents (e.g., AlphaZero, MCTS, Value Networks, Process Reward Models).**
In checkers, the classisical design relies on the exploration and
manual designed evaluation function to imporove decision making. But the modern deep Reinforcement learning agents suggest the move while a network estimates the likelihood of winning from given position and it lerns through experience rather than relying one the manual design but it would require adapting and training the system for that game.