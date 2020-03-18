# Toy Robot

#### Table Of Contents
[Description](#description)
[Configuration and Instruction](#configuration-and-Instruction)
[Robot Operating Instructions](#robot-operating-instructions)
[Testing Instructions](#testing-instructions)


### Description

- The application is a simulation of a toy robot moving on a square tabletop, of dimensions 5 units x 5 units.
- There are no other obstructions on the table surface.
- The robot is free to roam around the surface of the table, but must be prevented from falling to destruction. Any movement that would result in the robot falling from the table must be prevented, however further valid movement commands must still be allowed.

### Configuration and Instruction

To run the app, you need:

* [Node.js](https://nodejs.org/en/download/)
* [npm](https://www.npmjs.com/)

Install dependencies, run `$ npm install` in root dir

Start the robot
```
$ npm start
```

### Robot Operating Instructions

This app only can read in commands of the following (textual) form

The Robot can read in commands of the following form (case insensitive):
```
- PLACE X,Y,F will put the toy robot on the table in position X,Y and facing F (NORTH, SOUTH, EAST or WEST).
- MOVE will move the toy robot one unit forward in the direction it is currently facing.
- LEFT and RIGHT will rotate the robot 90 degrees in the specified direction without changing the position of the robot.
- REPORT will announce the X,Y and F of the robot. This can be in any form, but standard output is sufficient.
```
* All other invalid commands would be ignored

Details:
- The origin (0,0) can be considered to be the SOUTH WEST most corner.
- The first valid command to the robot is a PLACE command, after that, any sequence of commands may be issued, in any order, including another PLACE command. The application should discard all commands in the sequence until a valid PLACE command has been executed.
- A robot that is not on the table can choose the ignore the MOVE, LEFT, RIGHT and REPORT commands.
- Input can be from a file, or from standard input, as the developer chooses.
- Provide test data to exercise the application.
- The application must be a command line application.


### Testing Instructions

Run `npm test:all` to run all the tests.

Or specify the path and file name of the spec to run a single test.

```
$ npm test [path and file name] // test specifc spec only
```
