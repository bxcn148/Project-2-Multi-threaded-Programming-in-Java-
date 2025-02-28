Download link :https://programming.engineering/product/project-2-multi-threaded-programming-in-java/

# Project-2-Multi-threaded-Programming-in-Java-
Project 2: Multi-threaded Programming in Java”
Objectives: To practice programming an application with multiple threads of execution and synchronizing their access to necessary shared objects.

Description: In this programming assignment you will simulate the package shipping management system for an automated package shipping operation similar to the one depicted here:

conveyor 4 conveyor 0

S0

S4

S1

conveyor 3

conveyor 1

S3

S2

2

This example package shipping operation has five routing stations (S0 – S4), each of which has an input and output conveyor connecting to conveyor lines (C0 – C4) that go elsewhere in the system. Resources were limited when the system was built so each conveyor going to the rest of the facility must be shared between two routing stations. Since each routing station simultaneously needs an input and output connection to function, access to the shared conveyor lines must be strictly regulated. Flow direction in not important in our simulation.

You have been hired to design a simulator for a new package management system being built with the same design, but possibly fewer/more stations. You are to implement this simulator in Java and have each routing station function in its own thread. A routing station moves packages from one of its connected conveyors to the other. A station’s workload is the number of times that a routing

Page 1

station needs to have exclusive access to the input and output conveyors during the simulation. Once a routing station is granted access to both conveyors it calls its doWork()method during which it will flow packages down each of its connected conveyors (of course it must verify that it has access and isn’t in conflict with another routing station). After the packages-in and packages-out methods are run, the workload of the routing station is reduced by 1 and the routing station will release both of the conveyors and signal waiting routing stations that the conveyors are available. After executing a flow and releasing its conveyors, a routing station should sleep for some random period of time. A routing station’s thread stops running when its workload reaches 0. To prevent deadlock, ensure that each routing station acquires locks on the conveyors it needs in increasing numerical order.

Restrictions:

Your source files should begin with comments containing the following information:

/*

Class: <name of class goes here>

*/

Do not use a monitor to control the synchronization in your program (i.e., do not use the Java synchronize statement).

Input Specification:

Your program must initially read from a text file (config.txt) to gather configuration information for the simulator. The first line of the text file will be the number of routing stations to use during the simulation. Afterwards, there will be one line for each station. These lines will hold the amount of work each station needs to process (i.e, the number of times it needs to move packages down the conveyor system). Only use integers in your configuration file, decimals will not be needed. You can assume that the maximum number of stations will be 10.

Output Specification:

Your simulator must output the following text to let the user know what the simulator is doing in each of these situations:

An input conveyor is set:

Routing Station X: input connection is set to conveyor number n

An output conveyor is set:

Routing Station X: output connection is set to conveyor number n

A stations workload is set:

Routing Station X: Workload set. Station X has a total of n package groups to move.

A station is granted access to its input conveyor:

Station X: holds lock on input conveyor n

A station is granted access to its output conveyor:

Station X: holds lock on output conveyor n

A station releasing access to its input conveyor:

Station X: unlocks input conveyor n

A station releasing access to its output conveyor:

Station X: unable to lock output conveyor – releasing lock on input conveyor n.

A station cannot obtain its second lock (on the output conveyor):

Station X: unlocks output conveyor n

A station successfully flows packages on input conveyor:

Station X: successfully moves packages into station on input conveyor n.

A station successfully flows packages on output conveyor:

Station X: successfully moves packages out of station on output conveyor n.

A station completes a flow:

Station X: has n package groups left to move.

A station has completed its workload:

* Station X: Workload successfully completed. * *

Deliverables:

Submit the following items via

All of your .java files.

A copy of a sample execution of your program, i.e., the output produced by your simulator (this should just be a text file). In your IDE redirect console output to a file, do this and include a copy of the output file produced by your program.
