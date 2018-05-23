# Getting Started: Python

> If you have a Github account: Fork the project and clone it locally, so you can share your amazing implementation with the world!

## Download the Starter Project

In a terminal window, navigate to the folder where you want to store this project (`cd <folder-name>`), and run:

```console
git clone https://github.com/socialgorithm/ultimate-ttt-py.git
```

After this, you'll have a folder named `ultimate-ttt-py`, which contains the player.

## Run the Random player

The starter project comes with a player that plays moves at random. You can ensure everything works as it
should by running this player against the `uabc` random player (so much randomness!):

`uabc -p -f "python3 run_player.py"`

> You need to have Python 3.6 or higher installed, see https://www.python.org/downloads/ for instructions

You should see output along the lines of:

```console
+----------------------------------+
|     Ultimate Algorithm Battle    |
+----------------------------------+
Starting practice mode (1 games)

Tie!
Games played: 1

Player A (player) wins: 0 (0%)
Player B (server) wins: 0 (0%)
Ties: 1 (100%)

Player 1 timeouts: 0
Player 2 timeouts: 0

Total time: 191.71ms
Avg game: 191.71ms
Max game: 191.71ms
Min game: 191.71ms
```

You are now ready to compete!

## Improve the Random player 

The random player plays by picking moves at random. You can view the code that does this by 
opening the `players/random.py` file. The code will be something like:

```python
class Random(StdOutPlayer):
    def __init__(self):
        super().__init__()

    def get_my_move(self) -> Tuple[MainBoardCoords, SubBoardCoords]:
        main_board_coords = self.pick_next_main_board_coords()
        sub_board = self.main_board.get_sub_board(main_board_coords)
        sub_board_coords = self.pick_random_sub_board_coords(sub_board)
        return main_board_coords, sub_board_coords

    def pick_next_main_board_coords(self) -> MainBoardCoords:
        if self.main_board.sub_board_next_player_must_play is None:
            return random.choice(self.main_board.get_playable_coords)
        else:
            return self.main_board.sub_board_next_player_must_play

    @staticmethod
    def pick_random_sub_board_coords(sub_board: SubBoard) -> SubBoardCoords:
        return random.choice(sub_board.get_playable_coords())
```

As you can see, the `get_my_move` method is the one you need to edit, it returns a tuple of `MainBoardCoords` and 
`SubBoardCoords` (which are essentially the same thing, they contain a `row` and a `column`).

To keep things simple, start off with editing the `players/random.py` file.

## Game Engine

There is a game engine provided that keeps track of the state of the game and does a lot of the heavy lifting
for you. This can be accessed through the `self.main_board` object, and you can consult
the [API Reference](https://ultimate-ttt-py.readthedocs.io/en/latest/) for all the available methods 

### Sources

Some folks prefer to view the source of the game engine directly rather than using the API reference. You can
find all the sources in the `engine/` directory.

## Continue: [Analyse Your Games](analyse_games.md)

--------

## Troubleshooting

#### Can't find the project!

After running `git clone` without errors you should have the project in the folder the terminal is in. To find out where this is type `pwd` (or `echo %cd%` on Windows).