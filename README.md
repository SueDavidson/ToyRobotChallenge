# ToyRobotChallenge
Toy Robot Challenge is a simulation of a toy robot moving on a square table top, of dimensions 5 units x 5 units.

Use Visual Studio 2017 to build and run - open file ToyRobotChallenge/ToyRobotChallenge.sln
As the code stands it will read and write from the console, 
but commenting Program.cs line 9
	IToyRobotIOHandler toyRobotIOHandler = new ToyRobotConsoleIOHandler();
and uncommenting Program.cs line 10
	IToyRobotIOHandler toyRobotIOHandler = new ToyRobotFileIOHandler();
will allow you to use files instead.  

Filenames can be altered in ToyRobotFileIOHandler.cs at lines 18 and 19. 

Output file will be created in the directory ToyRobotChallenge\ToyRobotChallengeApp\bin\Debug.  
It will be added to rather than created new each run, but a line of text in the file indicates the start of each run.

Input is not case-sensitive and output is always in uppercase.  

Valid commands are
PLACE X,Y,F [where X and Y are ints between 0 and 4, and F is one of NORTH, EAST, SOUTH, WEST]
MOVE
LEFT
RIGHT
REPORT

PLACE will put the toy robot on the table in position X,Y and facing NORTH, SOUTH, EAST or WEST.  
The origin (0,0) can be considered to be the SOUTH WEST most corner. 
MOVE will move the toy robot one unit forward in the direction it is currently facing.
LEFT and RIGHT will rotate the robot 90 degrees in the specified direction without changing the position of the robot.
REPORT will announce the X,Y and F of the robot.
A robot that is not on the table (ie has not been placed) will ignore the MOVE, LEFT, RIGHT and REPORT commands.
All commands including PLACE can be issued multiple times.

All commands before a valid PLACE command are ignored, and all invalid commands are ignored.
All commands that would take the robot off the 5x5 tabletop are ignored.
No exception messages are given.

Examples:

input of 
PLACE 0,0,NORTH 
MOVE 
REPORT 
gives output of : 0,1,NORTH

input of 
PLACE 1,2,EAST
MOVE
MOVE
LEFT
MOVE
REPORT
gives output of: 3,3,NORTH
