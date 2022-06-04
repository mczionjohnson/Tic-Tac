# stage 1
child: square
component so we extend react component

parent: board
component so we extend react component

# stage two
child: square
class

parent: Board 
component so we extend react component

# stage 3 
2nd child: square
class

1st child: board
component so we extend react component

parent: Game 
component so we extend react component

# The plan

When a Square is clicked, the onClick function provided by the Board is called. Here’s a review of how this is achieved:

The onClick prop on the built-in DOM <button> component tells React to set up a click event listener.
When the button is clicked, React will call the onClick event handler that is defined in Square’s render() method.
This event handler calls this.props.onClick(). The Square’s onClick prop was specified by the Board.
Since the Board passed onClick={() => this.handleClick(i)} to Square, the Square calls the Board’s handleClick(i) when clicked.



We set an array of 9 element and made it null by default

Note how in handleClick, we call .slice() to create a copy of the squares array to modify instead of modifying the existing array. We made it immutable so we can build history and undo our click by going back a step in the memory saved.



we made X default so when taking turns with 'X' and 'O'

Each time a player moves, xIsNext (a boolean) will be flipped to determine which player goes next and the game’s state will be saved

Copy this helper function and paste it at the end of the file:

Given an array of 9 squares, this function will check for a winner and return 'X', 'O', or null as appropriate.

We will call calculateWinner(squares) in the Board’s render function to check if a player has won. If a player has won, we can display text such as “Winner: X” or “Winner: O”. We’ll replace the status declaration in Board’s render function with this code:

# Creating History
# stage three

We can now change the Board’s handleClick function to return early by ignoring a click if someone has won the game or if a Square is already filled: by using an if statement in the handleClick

Delete the constructor in Board.
Replace this.state.squares[i] with this.props.squares[i] in Board’s renderSquare.
Replace this.handleClick(i) with this.props.onClick(i) in Board’s renderSquare.