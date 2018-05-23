# Competing

So, you've written the smartest AI algorithm to play Ultimate Tic Tac Toe? Let's play against everyone else's!

Each client will connect to our server, and they will play 100-1000 games against each other in a tournament style competition, where algorithms will keep advancing towards the final round.

Please make sure that you have [tested your client locally](analyse_games.md) and it works. Ideally it should beat the random implementation every single time consistently.

## Connecting to the Server

Similarly to local testing, you'll be using the `uabc` client to connect. Simply run the following command:

```
$ uabc --host {server host} --token {your token} -f "node path/to/player.js"
```

* The `host` will be given to you on the competition day.
* The `token` can be anything unique that identifies your team. The server won't allow duplicate tokens.

Once connected just leave the terminal window open, the client will wait for server commands, and play when it's told to play.

If your player crashes simply run the command again, if you were in the middle of the game you will have lost it, but you can continue playing after that. The server will handle all these cases (hopefully).