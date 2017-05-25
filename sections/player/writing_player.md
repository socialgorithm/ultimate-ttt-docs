# Writing a Player

We're going to write an algorithm that can play UTTT, exciting right? :)

At the most basic level, a player needs to be able to calculate a **valid move**, and receive **opponent moves**. Every time it receives a move from its opponent it will run some calculations, and return what it considers to be the optimal move.

A simple start would be to have a program that does just that:

```js
// pseudo-code example of the most basic methods
addOpponentMove(board, move) {
    // store his move
}

addMove(board, move) {
    // store our move
}

getMove() {
    // calculate a new move
    return {
        board: ...,
        move: ...
    };
}
```

The problem with his is that we need to store and know the **game state** - have a board, calculate whether a player has won, check if a move is valid...

We have already written the code to do that in the following languages:

* [JavaScript](https://github.com/socialgorithm/ultimate-ttt-js)
* [Python](https://github.com/socialgorithm/ultimate-ttt-py)

Both projects contain the documentation on how to use them and what API they expose.

## Initial implementations

On top of writing the game engine, we have created initial implementations of players that are ready to go. They are choosing their moves at random at the moment though, so you'll have to give them some AI ;)

To get started, fork any of the following repositories and hack away!

* [JavaScript](https://github.com/socialgorithm/uttt-player-js)
* [Python](https://github.com/socialgorithm/uttt-player-py)

> These implementations use the game engines linked above - please visit those repositories for API documentation on what attributes and methods the engines expose!

Head over to [Testing locally](testing_locally.md) to see how you can start playing games with your algorithm!