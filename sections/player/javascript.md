# Getting Started: Javascript

> If you have a Github account: Fork the project and clone it locally, so you can share your amazing implementation with the world!

## Download the Starter Project

In a terminal window, navigate to the folder where you want to store this project (`cd <folder-name>`), and run:

```console
git clone https://github.com/socialgorithm/uttt-player-js.git
```

After this, you'll have a folder named `uttt-player-js`, which contains the player.

## Set up

After you've cloned the repository, cd into the project folder (`cd uttt-player-js`), and run the following command to install the dependencies:

```bash
npm install
```


The `player.js` file does the stdin/stdout work, and you shouldn't edit it. It requires the file `src/defensive/logic.js`, which is the one you could start with.

Inside the `src` folder you'll find three implementations:

* `defensive/logic.js` - is a good start, as it already provides some minimal logic to compete.
* `firstAvailable/logic.js` - selects the first available valid move, whatever that is.
* `random/logic.js` - selects any valid move at random.

It's interesting to look at each of these to see how they implement the logic and learn about it before starting to make changes.

> We have prepared [some ideas](ideas.md) on how to write the AI for your player that may help you out!

## Continue: [Running Locally](analyse_games.md)

--------

## Troubleshooting

#### Can't find the project!

After running `git clone` without errors you should have the project in the folder the terminal is in. To find out where this is type `pwd` (or `echo %cd%` on Windows).