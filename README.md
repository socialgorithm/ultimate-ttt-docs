# Ultimate TTT Algorithmic Competition

We are going to be playing a game of Ultimate Tic Tac Toe (you'll learn all about it soon). This documentation will help you write an intelligent algorithm.

**Please read everything carefully!**

> something about socialgorithm, link to get involved

*Good Luck!*

## Before You Arrive

These are the minimum requirements to participate in the coding competition:

1. Have a **code editor**. The choice here is basically infinite, so I'll list the most popular and you can choose any.
    * [Visual Studio Code](https://code.visualstudio.com/) _(recommended)_
    * [Sublime Text](https://www.sublimetext.com/3)
    * [Atom](https://atom.io/)
    
    > Subjective, I know, and you might be screaming "emacs/vim are SO much better". We know them, and use them (vim personally), but this is targeting people _without_ a code editor in their machine already.

1. Install [Git](https://git-scm.com/downloads)
1. Install [NodeJS >7](https://nodejs.org/en/download/current/)
1. Install the competition client:
    ```bash
    npm install -g @socialgorithm/uabc
    ```

Test that it works by running:

```console
uabc --version
```

And you should see a version number (e.g. 6.0.0)

## Continue: [Game Rules](sections/uttt/ultimate_tic_tac_toe.md)

-----

## Troubleshooting

#### Permission Denied / EACCES

If you see an **EACCES** error when you try to install a package globally: See the [npm docs on permissions](https://docs.npmjs.com/getting-started/fixing-npm-permissions).

#### Lots of warning messages on Windows

If after running `npm install` you see loads of warning messages in red/yellow, this is typically ok and everything should work.