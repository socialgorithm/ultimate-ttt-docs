There are endless ways in which you can write the logic for your player, which is part of the fun! But here we're going to explore two ideas.

The first is easier to implement, while the second is harder but should choose the best move every time.

## Idea 1: Heuristics

How do we choose a move without examining every single combination of moves? We try to see how good/bad a move is by analysing some of its characteristics.

For instance, if the opponent can win after you play a certain move, that makes it a pretty poor choice :)

What we can do is assign an initial score of 0 to each available move in the board we have to play in. Assuming it's empty our initial "score matrix" will look like this:

```
[
  [0, 0, 0],
  [0, 0, 0],
  [0, 0, 0],
]
```

Now we define a bunch of **conditions** we'll be looking for, and a score modifier for each condition.

Examples:

1. If the move wins me the small board -> +1
1. If the move loses me the small board -> -1
1. If the board where I'll send the opponent can be won by them -> -1
1. If the board where I'll send the opponent is winnable by me -> -1 (because they might block the move)
1. If by playing this move I block 2 in a row from the opponent -> +1

You should also adjust the modifiers, and keep testing the performance of your player against a random implementation, or against the same implementation with different scores, to optimize for the best combination.

If you apply this algorithm correctly, after running the conditions you have defined you'll be left with something like this:

```
[
  [3, -1, 2],
  [1, 2, 0],
  [-4, -2, 1],
]
```

And we can see that the move in `[0, 0]` is the best with a score of `3`.

## Idea 2: Monte Carlo Tree Search

[MCTS](https://en.wikipedia.org/wiki/Monte_Carlo_tree_search) also uses heuristics, but is a more thorough algorithm typically used in similar situations.

The wikipedia page linked above does a really good job of explaining the basics, and enough is already available online about this algorithm so we won't go into more detail.

Keep in mind that for the competition there is a timeout per move, so make sure that you tune the algorithm appropriately.

------

You should now be ready to learn [how to test your player locally](analyse_games.md)!