# Ultimate Tic Tac Toe

![Ultimate Tic Tac Toe board, with an animation for some rounds](/assets/uttt.gif)

This is the board for an **Ultimate Tic Tac Toe** game, it's essentially a collection of nine small *regular* Tic Tac Toe games.

On each turn, the valid small board is **highlighted in yellow**. Each player's move is displayed in *blue/red*.

You'll be playing on the big board, but in order to *"win"* each cell, you have to win the **game within that cell**.

The first player can play in any cell of any of the small boards. The coordinates of the **move in the small board** determine which *board* the next player has to use to play.

## Rules

1. You only play on the small boards.
1. The first player can play on any cell of any small board.
1. You must play on the small board that corresponds to the cell the other player played at.
1. If you are *sent* to a board that has been won already, you must play on any other board. *(Some people play with variations of this rule, but we believe this makes for the most interesting algorithms)*
1. To win the game you must have 3 in a row in the big board in any direction.

### Example

If this is the first move of the game:

![Example of a first move](/assets/3-first-move.jpg)

Then the other player has to play on the top right board:

![Board where the next player has to play in](/assets/4-second-move.jpg)

## Playing

The game may seem simple at first, but the fact that you get to decide where your opponent plays next means that you'll have to look ahead several turns to decide what the best move is.

You should start by playing at least once on paper with a friend, to get an idea of how the game goes. Sometimes giving up one of the smaller games is necessary to win the big one!

You are now ready to [start writing your own player](../player/writing_player.md)!