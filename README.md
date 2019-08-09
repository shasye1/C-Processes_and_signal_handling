# C-Processes_and_signal_handling
To practice creating processes and signal handling.

## Overview:

An adult (the gameOfficial) lets some number of children take turns hitting a pinata. With probability 1/20 (as computed by a pinata process) the pinata will bust, and the winning child get all the candy.

In this assignment we'll make 3 programs:

a) A pinata program that waits until it receives SIGUSR1. It will then
  + send SIGUSR1 with probability 19/20, or
  + send SIGUSR2 with probability 1/20


to the process that signalled it.


b) A child program who hits the pinata.
  + It waits for its parent process (the gameOfficial) to send it SIGUSR1 and tell the child that it is that child's turn.
  + It then sends SIGUSR1 to the pinata-processes.
  + If it gets back SIGUSR1 it knows it failed to break the pinata, and it sends SIGUSR1 back to the gameOfficial.
  + However, if it gets back SIGUSR2 is knows it did break the pinata, and it sends SIGUSR2 back to the gameOfficial.
  
  
c) A gameOfficial program.
  + It asks the user for:
    + the number of pinata-whacking children to make
  + It makes all the processes
  + It regulates the game, and
  + It tells the processes to end after the game is finished.

### Output:

$ ./gameOfficial 


Number of children? 2


Child 0's turn:


Child 0: I'm going to whack at it!


Child 0: A swing and a miss!


Child 1's turn:


Child 1: I'm going to whack at it!


Child 1: Curses!  I think I just weakened it for the next child!


Child 0's turn:


Child 0: I'm going to whack at it!


Child 0: Curses!  I think I just weakened it for the next child!


Child 1's turn:


Child 1: I'm going to whack at it!


Child 1: Damn, I missed the pinata completely!


Child 0's turn:


Child 0: I'm going to whack at it!


Child 0: A swing and a miss!


Child 1's turn:


Child 1: I'm going to whack at it!


Child 1: A swing and a miss!


Child 0's turn:


Child 0: I'm going to whack at it!


Child 0: Hey I hit it!  What's that thing made of?  Kevlar?


Child 1's turn:


Child 1: I'm going to whack at it!


Child 1: Curses!  I think I just weakened it for the next child!


Child 0's turn:


Child 0: I'm going to whack at it!


Child 0: A swing and a miss!


Child 1's turn:


Child 1: I'm going to whack at it!


Oh yeah!  All that candy is MINE baby!


Child 1 won!


Child 0 stopping


4405 has finished.


Child 1 stopping


4406 has finished.


Pinata stopping


4404 has finished.
