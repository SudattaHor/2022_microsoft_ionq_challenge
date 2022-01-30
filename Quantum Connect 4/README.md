# QuantumConnect4

## Outline (Preview)

- List of Moves in order of time
- List of Moves based on column (may need to remove Moves when it's measured and no longer relevant to that column) (stored as Index)
- class Move
  - Index (location in the list of Moves)
  - Column_1
  - Column_2
  - Prob_1
  - Prob_2
  - Player
- Board
  5 rows x 5 columns
- Display for board?
- Measure column
  - Iterate over Moves in the column 
    - If Move has Prob_1 less than maxProb
      - Get 0 or 1 from qc
      - Change to: Prob_1=maxProb, Prob_2=0, Column_1=measurement result, Column_2=doesn't matter
- Game logic
  - Is a move valid (# of Moves in that )
  - Interaction with player
- List to say which columns are deterministically full
- Check for game end (when all columns are full)
  - Simulation of classical connect 4

## Rules

- Players can play a piece into a superposition of two columns. For example, 1/2 C1 + 1/2 C2 is a move that has a 50% chance of landing in column 1 and a 50% chance of landing in column 2.
- A column is measured when a player wants to play into a potentially filled column.
- If both columns are measured to have space, the player's piece will be played as normal
- If one column is measured to be full and the other to have space, then the piece will be placed into the latter column with 100% certainty.
- If both columns are measure to be full, the player's piece will not be played.
- A player wins if they get a row, column, or diagonal of four of their adjacent pieces.
- The game ends when a player wins or if no more moves can be made.