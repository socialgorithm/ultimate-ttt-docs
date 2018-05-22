# Getting Started: Python

> If you have a Github account: Fork the project and clone it locally, so you can share your amazing implementation with the world!

## Download the Starter Project

In a terminal window, navigate to the folder where you want to store this project (`cd <folder-name>`), and run:

```console
git clone https://github.com/socialgorithm/uttt-player-py.git
```

After this, you'll have a folder named `uttt-player-py`, which contains the player.

## Set up

Now make sure you have Python3 installed, run `python3 -v` and ensure it prints 3.6.

> If you don't have Python3 installed, see https://www.python.org/downloads/ for instructions, and download the latest version (3.6).

Once that's done, you need to install the `ultimate_ttt` package on which this player depends:

```bash
$ pip3 install ultimate_ttt
```

We have provided the `ultimate_ttt_player/random_player.py` file to get you started.

The only method you need to edit to improve this player is `get_my_move` (line 25) - and any other method that this would call. You can see that the random player just picks a valid board at random, then a valid position within that board. You can obviously do better... ;)

> We have prepared [some ideas](ideas.md) on how to write the AI for your player that may help you out!

## Continue: [Running Locally](testing_locally.md)

--------

## Troubleshooting

#### Can't find the project!

After running `git clone` without errors you should have the project in the folder the terminal is in. To find out where this is type `pwd` (or `echo %cd%` on Windows).