# Testing Locally

> If you've started from one of the [sample implementations](writing_player.md#initial-implementations) then you can skip to [Installing the Client](#installing-the-client)!

In order to test locally/compete, we have written a small client utility that will execute your algorithm and handle everything.

This means that your player needs to be able to read/write to [stdin/stdout](https://en.wikipedia.org/wiki/Standard_streams) *(Don't worry, pretty much every programming language does this easily)*.

Our client will execute your player, and send commands like `move`, or `opponent 1,0;1,1`.

## Client Commands

The client will execute your algorithm as a child process, and pipe commands to its stdin/stdout.

For you, this means that you'll do something like the following (JavaScript pseudo-code):

```js
process.on('stdin', doSomething); // read commands

console.log('command'); // write commands
```

This means that to get debug statements on the console you'll need to use **stderr**. Every language usually has a function to log to it. In JavaScript you can just use `console.error('text')` for example.

## Listening

The uabc client will send you one of the following:

|Command|Expects response|Description|
|-------|----------------|-----------|
|`init`|No|The server is telling you to start the game - choose any board and move that you want|
|`waiting`|No|The server is telling you that the other player is not ready yet.|
|`move`|Yes|Move request, since you can answer directly to an opponent move, this is usually not necessary|
|`opponent x,y;x,y`|Yes|Sent after an opponent move, it contains their move data in the form `board.x, board.y; move.x, move.y`. After receiving this you can directly answer with your move|

## Responding
The only possible response at any given time is a move. If you answer out of place you will lose the game.

### Response format
`x,y;x,y` - Where the first coordinates are the board, and the second are the move (`board.x, board.y; move.x, move.y`)

# Example

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

## Installing the Client

> You'll need to have [Nodejs and NPM installed](https://nodejs.org/en/download/) in your computer.

Install the executable:

```bash
$ npm install -g @socialgorithm/uabc
```
Verify the installation by running:

```bash
$ uabc --version
```

## Playing Locally

To start a local practice round, with logging to file and console, run:

```
$ uabc -p --log --verbose -f "node path/to/player.js"
```

* `-p` puts the client in practice mode
* `--log` enables logging to a file
* `--verbose` enables logging to the console
* `-f` defines the path to your executable player (for scripting languages like JavaScript or Python you may have to add `node` and `python` to the path, as seen in the example)

Logging to a file is very useful because you can then [upload your log file](https://uttt.socialgorithm.org/replay) to see the games and analyze the moves one by one.

For an explanation of all the options run `uabc -h`.