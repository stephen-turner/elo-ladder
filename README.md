# Elo-ladder [![Build Status](https://travis-ci.org/stephen-turner/elo-ladder.png)](https://travis-ci.org/stephen-turner/elo-ladder)

_An Elo-rating based backgammon ladder competition manager_

The algorithm is the Elo-Kaufman algorithm, as popularised by FIBS.
It is described at http://www.bkgm.com/faq/Ratings.html.

This project is forked from Rob Hoes and Simon Beaumont's chess ladder, https://github.com/robhoes/elo-ladder.
Note that the output includes some concepts that are not applicable to
backgammon, such as the number of games as white and black, and drawn games.
This is intentional in order to keep the code as little diverged from upstream
as possible; meaningless statistics are filtered out client-side.

## Getting involved
The results of the ladder are automatically published at
http://stephen-turner.github.io/elo-ladder.

Here you can also find instructions on adding yourself to the ladder and
recording games that you have played.

## Commandline usage

```
NAME
       ladder - An Elo ladder system

SYNOPSIS
       ladder COMMAND ...

COMMANDS
       history
           Compute and print historic ratings of players for plotting

       print
           Compute and print ELO ladder

OPTIONS
       --help[=FMT] (default=pager)
           Show this help in format FMT (pager, plain or groff).

       --version
           Show version information.

       Use `ladder COMMAND --help' for help on a specific command.
FILE-FORMATS
       The PLAYERS file should be in CSV format:

       Syntax:
           <ID>,<Full name>,<Elo-rating>,<active>

       Where ID can be any unique string, Elo-rating is the starting
       rating for the player as an integer, and active indicates
       whether the player is retired or not.

       Example:
           X-22,Paul Magriel,1870,true

       
       The GAMES file should be in CSV format:

       Syntax:
           <Date>,<Player 1's ID>,<Player 2's ID>,<LENGTH>,<RES>

       Where the date is in ISO 8601 format (yyyy-mm-dd); IDs match those
       listed in the PLAYERS file; LENGTH is the match length (winning score);
       and RES is either 1 or 0 in the case of a win or loss for Player 1 respectively.

       Example:
           2013-11-21,X-22,robertie,7,1

BUGS
       Please report bugs by opening an issue on the Elo-ladder project page
       on Github:
           https://github.com/stephen-turner/elo-ladder

```
