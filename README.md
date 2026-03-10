# Custom Interpreter

A small programming language interpreter written in Python.

## Features
- print statements
- variables
    Syntax:
    - var x = 5 {this assigns the value of x to 5}
    - you can now use math operations in variables
    Eg: var x = 4 5 add {it assigns the value of x to 9}
    - you can also use variables in math operations
    Eg: var x = 4 5 add
        var y = x 10 add {it assigns the value of y to 14}
    - you can also use in loops
    Eg: var x = 4
        for x
            print i
        end {prints 4 four times}
- stacks and their operations
    Syntax:
    - stack x [1,2,3] {creates a new stack}
    - stack append variable_name value
    - stack pop variable_name
    - stack del variable_name index 
    - for loop over stacks
        Syntax:
        - stack name [1,2,3]
        - for variable_name in stack_name
            print variable_name
          end
- arithmetic operations
    Syntax:
    - math n1 n2 op
- comparision
    Syntax
    - math 5 7 gt {returns False}
    - math x = 5 7 gt {creates {'x': 'False'}}
- multi-number math operations
- operator dispatch table
- more features will be added

## Example program

var x 10
var y 5

math x y add
print "done"

## Run

python main.py nameOfTheProgram