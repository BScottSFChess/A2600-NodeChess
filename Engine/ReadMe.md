# Engine substructures
This chess engine will require, just like all others, a few subunits that allow for it to achieve its ultimate end goal - that being of choosing the next best move to play.

The game must be managed in a way that allows for complex computation to occur with plenty of “wiggle room” for “edge cases.” As such, we want to place little emphasis initially on the amount of engine nodes that are used in the network of Atari systems, only to then focus on such a concept later to attempt to keep strength maintained while making the system less distributed and large.

That said, our subsystem structure requires the following functions to be performed :

1. Adequate opening play by inclusion of a small opening book

2. A position evaluator

3. A NegaMax search algorithm with alpha beta pruning

4. A continuation generator that produces possible next moves

5. A game state representator system

6. A pre-game menu that allows the player to indicate what side it is to play as along with any additional settings for the search system, such as how many game plies to search down to

7. A system to convert the internal square representation system out to algebraic coordinates for easier understanding of what is to be played


# Functions of the individual consoles
Console 1 - This first Atari is the system that will hold all of the extremely basic variables and which will be used as an interface between the user and the system. It is to store the color the engine will play as, the search depth in plies, the most recent moves made by the two players, and the number of pieces per type of piece per player color that are present on the board at any given moment.

Console 2 - This secondary console will store in its variables the positions of each white piece on the board at any given instant. It will also store the rights to whether or not En Passant is permitted for that player or not in either direction for that player on a file by file basis. 0 = Not permitted, 1 = On the left, 2 = On the right, 3 = Both sides.

Console 3 - Identical to console two except it is now for the black pieces.

Console 4 - This console will use the upper thirteen variables of the alphabet for white and the lower thirteen variables of the alphabet for black as the means by which castling rights are permitted. For each 13 variables, they are organized by the following purposes as boolean values 

     1 : Has king not moved?
     
     2 : Has queenside rook not moved?
     
     3 : Has kingside rook not moved?
     
     4 : Is King not in check?
     
     5 : Is f1 not in check?
     
     6 : Is g1 not in check?
     
     7 : Is f1 unoccupied?
     
     8 : Is g1 unoccupued?
     
     9 : Is c1 not in check?
     
     10 : Is d1 not in check?
     
     11 : Is b1 unoccupied?
     
     12 : Is c1 unoccupied?
     
     13 : Is d1 unoccupied?

Console 5 - 
