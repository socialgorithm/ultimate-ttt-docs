# Testing Locally

> If you haven't installed the client utility `uabc` please go through the ["Before You Arrive" section](../../README.md).

## Playing Locally

To start a local practice round, with logging to file and console, run:

> **JavaScript Players:**

```console
uabc -p --log --verbose -f "node path/to/player.js"
```

> **Python Players:**

```console
uabc -p --log --verbose -f "python3 path/to/player.py"
```

* `-p` puts the client in practice mode
* `--log` enables logging to a file
* `--verbose` enables logging to the console
* `-f` defines the path to your executable player (for scripting languages like JavaScript or Python you may have to add `node` and `python` to the path, as seen in the example)

For an explanation of all the options run `uabc -h`.

### ProTip! Analyse Your Games

Logging to a **file** is very useful because you can then *[upload your log file](https://uttt.socialgorithm.org/replay)* to see the games and analyze the moves one by one.

![Game Analysis](/assets/replay.gif)

Seriously, this is going to be *very* useful, **try it**!

## Continue:

### [Ideas for Your Player](ideas.md)
### [Competing](competing.md)
