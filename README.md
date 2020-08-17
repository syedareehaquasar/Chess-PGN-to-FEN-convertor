# PGN to FEN Parser

This code takes PGN text file, used in games of chess, as input, and prints the final position of the board after the game, in the FEN Notation.


# What is FEN Notation

[wikipedia](https://en.wikipedia.org/wiki/Forsyth%E2%80%93Edwards_Notation#:~:text=Forsyth%E2%80%93Edwards%20Notation%20(FEN),game%20from%20a%20particular%20position.)

A FEN "record" defines a particular game position, all in one text line and using only the ASCII character set. A text file with only FEN data records should have the file extension ".fen".[4]

A FEN record contains six fields. The separator between fields is a space. The fields are:[5]

Piece placement (from White's perspective). Each rank is described, starting with rank 8 and ending with rank 1; within each rank, the contents of each square are described from file "a" through file "h". Following the Standard Algebraic Notation (SAN), each piece is identified by a single letter taken from the standard English names (pawn = "P", knight = "N", bishop = "B", rook = "R", queen = "Q" and king = "K"). White pieces are designated using upper-case letters ("PNBRQK") while black pieces use lowercase ("pnbrqk"). Empty squares are noted using digits 1 through 8 (the number of empty squares), and "/" separates ranks.

Active color. "w" means White moves next, "b" means Black moves next.

Castling availability. If neither side can castle, this is "-". Otherwise, this has one or more letters: "K" (White can castle kingside), "Q" (White can castle queenside), "k" (Black can castle kingside), and/or "q" (Black can castle queenside). A move that temporarily prevents castling does not negate this notation.

En passant target square in algebraic notation. If there's no en passant target square, this is "-". If a pawn has just made a two-square move, this is the position "behind" the pawn. This is recorded regardless of whether there is a pawn in position to make an en passant capture.[6]

Halfmove clock: This is the number of halfmoves since the last capture or pawn advance. This is used to determine if a draw can be claimed under the fifty-move rule.

Fullmove number: The number of the full move. It starts at 1, and is incremented after Black's move.

## Sample Input

Starting FEN position - rnbqkbnr/pppppppp/8/8/8/8/PPPPPPPP/RNBQKBNR w KQkq - 0 1

PGN file:

[Event "Earl tourn"]

[Site "?"]

[Date "1906.??.??"]

[Round "?"]

[White "Giese"]

[Black "Alekhine, Alexander"]

[Result "0-1"]

[WhiteElo ""]

[BlackElo ""]

[ECO "C47"]


1.e4 e5 2.Nf3 Nc6 3.d4 exd4 4.Nxd4 Nf6 5.Nc3 Bb4 6.Nxc6 bxc6 7.Qd4 Qe7 8.f3 d5

9.Bg5 O-O 10.O-O-O Bc5 11.Bxf6 gxf6 12.Qa4 Be3+ 13.Kb1 d4 14.Ne2 c5 15.Nc1 Be6

16.Bc4 Rfb8 17.Nd3 Rb6 0-1


## Sample Output

respective moves:

rnbqkbnr/pppppppp/8/8/8/8/PPPPPPPP/RNBQKBNR w KQkq - 0 1

rnbqkbnr/pppppppp/8/8/4P3/8/PPPP1PPP/RNBQKBNR b KQkq - 0 1

rnbqkbnr/pppp1ppp/8/4p3/4P3/8/PPPP1PPP/RNBQKBNR w KQkq - 0 2

rnbqkbnr/pppp1ppp/8/4p3/4P3/5N2/PPPP1PPP/RNBQKB1R b KQkq - 1 2

r1bqkbnr/pppp1ppp/2n5/4p3/4P3/5N2/PPPP1PPP/RNBQKB1R w KQkq - 2 3

r1bqkbnr/pppp1ppp/2n5/4p3/3PP3/5N2/PPP2PPP/RNBQKB1R b KQkq - 0 3

r1bqkbnr/pppp1ppp/2n5/8/3pP3/5N2/PPP2PPP/RNBQKB1R w KQkq - 0 4

r1bqkbnr/pppp1ppp/2n5/8/3NP3/8/PPP2PPP/RNBQKB1R b KQkq - 0 4

r1bqkb1r/pppp1ppp/2n2n2/8/3NP3/8/PPP2PPP/RNBQKB1R w KQkq - 1 5

r1bqkb1r/pppp1ppp/2n2n2/8/3NP3/2N5/PPP2PPP/R1BQKB1R b KQkq - 2 5

r1bqk2r/pppp1ppp/2n2n2/8/1b1NP3/2N5/PPP2PPP/R1BQKB1R w KQkq - 3 6

r1bqk2r/pppp1ppp/2N2n2/8/1b2P3/2N5/PPP2PPP/R1BQKB1R b KQkq - 0 6

r1bqk2r/p1pp1ppp/2p2n2/8/1b2P3/2N5/PPP2PPP/R1BQKB1R w KQkq - 0 7

r1bqk2r/p1pp1ppp/2p2n2/8/1b1QP3/2N5/PPP2PPP/R1B1KB1R b KQkq - 1 7

r1b1k2r/p1ppqppp/2p2n2/8/1b1QP3/2N5/PPP2PPP/R1B1KB1R w KQkq - 2 8

r1b1k2r/p1ppqppp/2p2n2/8/1b1QP3/2N2P2/PPP3PP/R1B1KB1R b KQkq - 0 8

r1b1k2r/p1p1qppp/2p2n2/3p4/1b1QP3/2N2P2/PPP3PP/R1B1KB1R w KQkq - 0 9

r1b1k2r/p1p1qppp/2p2n2/3p2B1/1b1QP3/2N2P2/PPP3PP/R3KB1R b KQkq - 1 9

r1b2rk1/p1p1qppp/2p2n2/3p2B1/1b1QP3/2N2P2/PPP3PP/R3KB1R w KQ - 2 10

r1b2rk1/p1p1qppp/2p2n2/3p2B1/1b1QP3/2N2P2/PPP3PP/2KR1B1R b - - 3 10

r1b2rk1/p1p1qppp/2p2n2/2bp2B1/3QP3/2N2P2/PPP3PP/2KR1B1R w - - 4 11

r1b2rk1/p1p1qppp/2p2B2/2bp4/3QP3/2N2P2/PPP3PP/2KR1B1R b - - 0 11

r1b2rk1/p1p1qp1p/2p2p2/2bp4/3QP3/2N2P2/PPP3PP/2KR1B1R w - - 0 12

r1b2rk1/p1p1qp1p/2p2p2/2bp4/Q3P3/2N2P2/PPP3PP/2KR1B1R b - - 1 12

r1b2rk1/p1p1qp1p/2p2p2/3p4/Q3P3/2N1bP2/PPP3PP/2KR1B1R w - - 2 13

r1b2rk1/p1p1qp1p/2p2p2/3p4/Q3P3/2N1bP2/PPP3PP/1K1R1B1R b - - 3 13

r1b2rk1/p1p1qp1p/2p2p2/8/Q2pP3/2N1bP2/PPP3PP/1K1R1B1R w - - 0 14

r1b2rk1/p1p1qp1p/2p2p2/8/Q2pP3/4bP2/PPP1N1PP/1K1R1B1R b - - 1 14

r1b2rk1/p1p1qp1p/5p2/2p5/Q2pP3/4bP2/PPP1N1PP/1K1R1B1R w - - 0 15

r1b2rk1/p1p1qp1p/5p2/2p5/Q2pP3/4bP2/PPP3PP/1KNR1B1R b - - 1 15

r4rk1/p1p1qp1p/4bp2/2p5/Q2pP3/4bP2/PPP3PP/1KNR1B1R w - - 2 16

r4rk1/p1p1qp1p/4bp2/2p5/Q1BpP3/4bP2/PPP3PP/1KNR3R b - - 3 16

rr4k1/p1p1qp1p/4bp2/2p5/Q1BpP3/4bP2/PPP3PP/1KNR3R w - - 4 17

rr4k1/p1p1qp1p/4bp2/2p5/Q1BpP3/3NbP2/PPP3PP/1K1R3R b - - 5 17
