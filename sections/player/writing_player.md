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

The problem with this is that we need to store and know the **game state** - have a board, calculate whether a player has won, check if a move is valid...

## Getting Started

We provide ready to use implementations that play at random, so you only have to improve the logic that picks the moves.

Pick the one for your language of choice:

* [Python](./python.md)
* [JavaScript](./javascript.md)
* [Other languages...](./other_languages.md)
