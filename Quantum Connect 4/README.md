# Quantum Connect 4

## Team

Derek Dong, Mayank Bhatia, Sudatta Hor

## Description

A traditional game of Connect4 but with a quantum twist. Typically, during a turn, players choose which column to play their piece. In Quantum Connect4, they are still able to choose a column, but now they can also choose a superposition of two different columns. The game also includes a measurement of this superposition, which collapses the move into one column or the other.

### Use of Quantum


In addition to the quantum concepts of superposition appearing as a game mechanic, quantum computing is also used as part of the backend computation! We use a simple quantum circuit composed of hadamard gates and measurements to generate bitstrings uniformly at random, and this functions as our random number generator for each of the measurements in the game.

This not only introduces an element of chance, but also an element of strategy to compete for information about the state of the boards.

## Instructions for Running the Project

1. Download main.ipynb
2. Open the quantum workspace on azure (https://aka.ms/aq/hackathon-notebooks)
3. Open main.ipynb and run it
4. Follow the prompts to play!

### Note on running:
The notebook can also be run locally. The difference is in the section "Random Number Generation." If running locally, run the subsection "Version for local testing." If running on Azure, run the subsection "Version on the quantum computer." There's also the option to switch to the IonQ simulator in the method "set_backend." Note, however, that we had issues with the simulator in that running 2k+1 shots gave a total of 2k counts in the result, which didn't work because we need tiebreaks.


## Rules

- Players can play a piece into a superposition of two columns. For example, 0.5 C1 + 0.5 C2 is a move that has a 50% chance of landing in column 1 and a 50% chance of landing in column 2.
- A column is measured when a player wants to play into a potentially filled column. When a column is measured, each move corresponding to a spot in the column will be measured in order from bottom to top.
- If both columns in the superposition of the move are measured to have space, the player's piece will be played as normal
- If one column is measured to be full and the other to have space, then the piece will be placed into the latter column with 100% certainty.
- If both columns are measured to be full, the player's piece will not be played.
- A player wins if they get a row, column, or diagonal of four of their adjacent pieces.
- The game ends when no more moves can be made.
  - Since many playthroughs of the game lead to states that are the superposition of some finished and some unfinished boards, we allow the entire board to be filled and then re-iterate over the moves played. By that time, every move must have been measured and has collapsed into a classical move. The winner, then, is the first player to obtain a "4-in-a-row;" the game is a draw if neither player achieves this.

## Benefit to Society


For those interested in learning about the fundamentals of quantum mechanics, Quantum Connect4 is a great way to visualize superposition. On the one hand, Connect 4 is not a game commonly studied in game theory. On the other, its simplicity to the layman makes it easy to understand the different elements at play. Quantum Connect 4 also seems to be a fantastic entrypoint to quantum game theory. Its low number of degrees of freedom (the number of moves is equal to the number of columns) makes it likely tractable for some of the earliest quantum AI, while its "gravity" mechanic makes it very interesting to study.

## Examples


![Example Board](https://github.com/SudattaHor/2022_microsoft_ionq_challenge/blob/main/Quantum%20Connect%204/qconnect4.gif)  
How the board might change as the game is played. Individual spots are filled based on the probability of the corresponding move collapsing to that column.  


![Example Interface](https://github.com/SudattaHor/2022_microsoft_ionq_challenge/blob/main/Quantum%20Connect%204/interface_sample1.png)  
An example of how interfacing with the game might look. Further improvements are on the horizon!

## Next Steps

Quantum Connect4 can be improved in several ways.

- Instead of limiting a move to be in a superposition between two columns, we can extend it to be in a superposition of several columns, up to the player's choice.
- Increasing board size
- Examine/evaluate common strategies.
- Improving the interface using button and slider user input.
- Improving the graphical representation of the board by visually including more information such as displaying the queue of each move.
- The game currently detects a win only at the end of the game. Next, we want to be able to identify a win during the game.

## Personal Notes

I enjoyed iQuHACK :) It's only been less than 2 days, but I am very proud of how far our team has come in terms of both project development and team bonding. -Sudatta

iQuHACK is my first-ever hackathon, and I'm very pleased. I didn't even know how the mechanics of quantum computing could apply to games at the start, but with my teammates' support here I am. I'll definitely be back next year! -Derek

My experience was unforgettable! I had so much fun coding, and I am so grateful for iQuHack and my awesome teammates! - Mayank

## Resources

Presentation slides: https://docs.google.com/presentation/d/11ASP5GFxbF01kt8On_yrPnLTJBlY-IXP2z4YlSZk_zc/edit?usp=sharing
