# Getting Started: Other Languages

You can use any language that you want to compete, but if you're not using Python or JavaScript there's a lot more code that you'll need to write.

## Communicating with the Competition Client

The competition client will execute your algorithm as a child process, and pipe commands to `stdin/stdout` using the following protocol:

|Command|Expects response|Description|
|-------|----------------|-----------|
|`init`|No|The server is telling you that a new game is starting, clear your state and await further commands|
|`waiting`|No|The server is telling you that the other player is not ready yet|
|`move`|Yes|Move request, since you can answer directly to an opponent move, this is usually only necessary once at the beginning of the game|
|`opponent row,col;row,col`|Yes|Sent after an opponent move, it contains their move data in the form `main_board.row, main_board.col; sub_board.row, sub_board.col`. After receiving this you can directly answer with your move|

If you output anything that doesn't fit that format to `stdout`, the client will redirect it to `stdout` so that you can see the output on the console.

### Responding
The only possible response at any given time is a move. If you answer out of place you will lose the game.

#### Response format
`row,col;row,col` - Where the first coordinates point to a sub_board/game of the main board, and the second are the cell co-ordinates of the sub board (`main_board.row, main_board.col; sub_board.row, sub_board.col`)

### Example

The following is a sample game from the point of view of player 1 (the input/output identifiers were added for clarity)

```
[input] init
[input] waiting
[input] opponent 0,0;2,2
[output] 2,2;2,0

[input] opponent 2,0;2,0
[output] 2,0;2,1

[input] opponent 2,1;2,1
[output] 2,1;0,1

...
```

## Game Engine

You'll need a data structure to store the current game state, whose turn it is, and some methods to calculate whether a game has been won. You can take a look at the game engines we have written in other languages for some inspiration:

* [JavaScript Game Engine](https://github.com/socialgorithm/ultimate-ttt-js)
* [Python Game Engine](https://github.com/socialgorithm/ultimate-ttt-py)

If you end up writing a game engine in any other language, please [get in touch](https://socialgorithm.org/#contact) so we can add it to the list!

> We have prepared [some ideas](ideas.md) on how to write the AI for your player that may help you out!

## Continue: [Running Locally](analyse_games.md)
