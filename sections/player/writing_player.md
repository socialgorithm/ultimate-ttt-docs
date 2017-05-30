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

## Initial implementations

On top of writing the game engine, we have created initial implementations of players that are ready to go. They are choosing their moves at random at the moment though, so you'll have to give them some AI ;)

1. Choose the language you want to start in (JavaScript or Python)
1. Go to Github and fork either of the following repositories
    * [JavaScript Starter Project](https://github.com/socialgorithm/uttt-player-js)
    * [Python Starter Project](https://github.com/socialgorithm/uttt-player-py)
1. Clone the repository locally: `git clone {repository url}`
1. Start working on your player, and check out the game engine docs for your language:
    * [JS Game Engine Documentation](https://socialgorithm.org/ultimate-ttt-js/)
    * [Python Game Engine Documentation](http://ultimate-ttt-py.readthedocs.io/en/latest/)


> These implementations use the game engines linked above - please visit those repositories for API documentation on what attributes and methods the engines expose!

Head over to [Testing locally](testing_locally.md) to see how you can start playing games with your algorithm!

### Game Engines & Documentation

Both of those projects use implementations of the Ultimate TTT game logic written by us. If you want to start a player from scratch you can use those directly, or port them to another language.

* [JavaScript](https://github.com/socialgorithm/ultimate-ttt-js)
* [Python](https://github.com/socialgorithm/ultimate-ttt-py)

Both projects contain the documentation on how to use them and what API they expose.

## JavaScript Starter Project

After you've cloned the repository, run the following command to install the dependencies:

```bash
$ npm install
```

You can now test the player using:

```bash
$ uabc -p -g 10 -f "node player.js"
```

The `player.js` file does the stdin/stdout work, and you shouldn't edit it. It requires the file `src/defensive/logic.js`, which is the one you could start with.

Inside the `src` folder you'll find three implementations:

* `defensive/logic.js` - is a good start, as it already provides some minimal logic to compete.
* `firstAvailable/logic.js` - selects the first available valid move, whatever that is.
* `random/logic.js` - selects any valid move at random.

It's interesting to look at each of these to see how they implement the logic and learn about it before starting to make changes.

## Python Starter Project

> You'll need to have python3 installed. See https://www.python.org/downloads/ for instructions, and download the latest version (3.6).

Once that's done, you need to install the `ultimate_ttt` package on which this player depends:

```bash
$ pip3 install ultimate_ttt
```

We have provided the `ultimate_ttt_player/random_player.py` file to get you started.

The only method you need to edit to improve this player is `get_my_move` (line 25) - and any other method that this would call. You can see that the random player just picks a valid board at random, then a valid position within that board. You can obviously do better... ;)

After you have made some changes, make sure to test your player works properly:

```bash
pip3 install . --upgrade
python3 setup.py test
```

If you think you have a good approach, you can test your player against a random one using uabc:

```bash
uabc -p -f -g 100 "python3 samples/random_player_wrapper.py"
```