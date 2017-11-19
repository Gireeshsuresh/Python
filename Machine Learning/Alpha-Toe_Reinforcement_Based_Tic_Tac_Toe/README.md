# Tic - Tac - Toe : [ The Game of Corss and Knots ]

This Repo is for the Tic-Tac-Toe implementation based on Reinforcement learning.

### Basic-1:- tic-tac-toe.py

Full code for running a game of tic-tac-toe on a 3 by 3 board.
Two players take turns making moves on squares of the board, the first to get 3 in a row, including diagonals, wins.

If there are no valid moves left to make the game ends a draw.

The main method to use here is play_game which simulates a game to the end using the function args it takes to determine
where each player plays.

The board is represented by a 3 x 3 tuple of ints. A '0' means no player has played in a space, '1' means player one has
played there, '-1' means the seconds player has played there.

The apply_move method can be used to return a copy of a given state with a given move applied.

This can be useful for doing Min-Max or Monte-Carlo sampling.

### Basic-2:- tic-tac-toe_x.py

Full code for running a game of tic-tac-toe on a board of any size with a specified number in a row for the win.

This is similar to tic_tac_toe.py but all relevant moves are parameterized by board_size arg that sets how big
the board is and winning_length which determines how many in a row are needed to win.

Defaults are 5 and 4. This allows you to play games in a more complex environment than standard tic-tac-toe.

Two players take turns making moves on squares of the board, the first to get winning_length in a row, including
diagonals, wins. If there are no valid moves left to make the game ends a draw.

The main method to use here is play_game which simulates a game to the end using the function args it takes to determine
where each player plays.

The board is represented by a (board_size) x (board_size) tuple of ints.
A 0 means no player has played in a space, 1 means player one has played there, -1 means the seconds player has played there.
The apply_move method can be used to return a copy of a given state with a given move applied.

This can be useful for doing Min-max or Monte-Carlo sampling.
