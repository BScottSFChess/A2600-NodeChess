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

7. A system to convert the internal square representation system out to algebraic coordinates for easier understanding of what is to be played.


# Subsystem 5 - Game state representator
Console 1 - This console will store in its variables the positions of each white piece on the board at any given instant; this will occur using the two functional place values of each variable as board coordinates, where the tenths place is the file and the ones place is the rank. It will also store the rights to whether or not En Passant is permitted for that player or not in either direction for that player on a file by file basis. 0 = Not permitted, 1 = On the left, 2 = On the right, 3 = Both sides.

Console 2 - Identical to console one except it is now for the black pieces.

Console 3 - This console will use the upper thirteen variables of the alphabet for white and the lower thirteen variables of the alphabet for black as the means by which castling rights are permitted. For each 13 variables, they are organized by the following purposes as boolean values 

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

Console 4 - This console is that which performs the utmost basic logic behind the castling rights. It will check for the ability to castle kingside or queenside for both players by simply adding the values of the certain conditions for castling queenside (1, 2, 4, 9, 10, 11, 12, 13), and kingside (1, 3, 4, 5, 6, 7, 8). Which then spits out one value stored either as a zero or a one which determines the ability to castle on either side for both players, based on whether or not the added value equals the total number of parameters checked in the first place.

Console 5 - This is the console which will then store information on each of the pawns and what type of piece they currently are. This will work on the basis that they are able to be five types.

     0 = Pawn

     1 = Bishop

     2 = Knight

     3 = Rook

     4 = Queen

The values will work such that there are 16 variables for each pawn on the board. Each pawn’s piece type variable is hardcoded to the pawn variable stored elsewhere in the system that the pawn is associated with. So, when a pawn promotes, the system then selects a value and upon doing so, the other portions of the system will change the movement form of the “pawn” to the other new piece it has been promoted to and use this new index here to change how many of each piece are on the board as is found in console one. The top eight variables A-H are white pawns and the next eight are black pawns.

# Subsystem 6 - Menu and data
Console 1 - This Atari is the system that will hold all of the extremely basic variables and which will be used as an interface between the user and the system. It is to store the color the engine will play as, the search depth in plies, the most recent moves made by the two players, and the number of pieces per type of piece per player color that are present on the board at any given moment. This is used in the evaluation on a basic level to determine raw point count.

# Subsystem 7 - Coordinate converter
Console 1 - This console will be used to convert incoming numbers from 1 to 64 out into coordinates. It does this by performing

     F = (INPUT-(INPUT%8))/10
     R = INPUT%8

Which then can be viewed in the variables page as “F is X / R is Y”

