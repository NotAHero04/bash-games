# TicTacToe... in 69 lines!

Tic Tac Toe is a game on a 3*3 board with 2 players who take turns marking each tile of the board with different marks, usually Xs and Os. The person who get a straight line of their mark wins.

This is the easiest game you can write in any programming language, because what you need to do is:

- Make a 3*3 board.
- Repeatedly do these:
  + Ask the player to choose the tile they want to mark.
  + Mark the tile if it's eligible.
  + Check if a straight line has been made. (For a simple game like this, you can actually list out all the possible lines. Nice!) If yes, end the game.
  + If not, check if the table has been filled. If not, swap the player, otherwise, end the game.

My implementation is as follows:

### Make a 3*3 board.

This is a no-brainer:
```
board=(. . . . . . . . .)
```
Bash only supports 1D arrays, so this is the best choice. Of course you can use any character instead of periods.

We also need to print it in a usable form. This piece of code will do the work:
```
for i in $(seq 0 2); do
  for j in $(seq 0 2); do
    result="$result ${board[((3*i+j))]}"
  done
  result="$result\n"
done
echo -n -e "$result"
result=""
```
`result` needs to be reset because we're not gonna print the board just once.

Next, we'll create a loop that ends when the game is over.
```
gameover=0
while [ $gameover -eq 0 ]; do
  <some code>
done
```
### Ask the player to choose the tile.
We haven't had any players yet. Out of the `while` loop, we set the first player:
```
player=1
```
To be continued...

