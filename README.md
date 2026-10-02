# A2600-NodeChess
A decentralized and human interfaced chess engine written across a series of Atari 2600 “Basic Programming” game cartridges.

The goal of this project is more or less to make a monster. A system that can play chess autonomously with no human thinking required aside from that of moving numbers from system to system at the discretion of a set of instructions as provided from that of a different set of Atari systems.

# The Architecture
The system is planned to work across a series of simultaneously powered Atari 2600 consoles each loaded with their own copy of “BASIC Programming.” There will be two distinct halves. One half will determine the routing of the data that is being used to calculate the best next move and can be found in the “DataRouter” directory within this project. This half of the network is split recursively in such a manner that the whole of the project is split into, where one half computes, and the other routes. Then the other half is simply the decentralized chess engine whose functionality works on the basis of it being like a lot of different small functions.

So, it looks almost like a layered system, where :

L4 is the master control layer.
L3 routes closely related routing systems.
L2 is the immediate routing between closely related systems in L1.
L1 is the base chess engine split across multiple consoles.

# Why?
The overall goal is to beat the official Atari “Video Chess” game cartridge at its maximum strength. For the purpose of the project is to build an “easy to use” system that can play high level chess despite what the limits of computer hardware at the time looked like for our eccentric user, of course, all at the cost of practicality.
