# Custom Interpreter

A small stack-based programming language interpreter written in Python.  
The interpreter reads programs from a file, parses commands, and executes them line by line.

This project demonstrates basic concepts used in interpreter design such as token execution, operator dispatch tables, variable environments, and control flow.

---

# Features

## Print Statements

Print values or strings.

Example:

```
print "Hello World"
```

---

## Variables

Variables store values that can be reused later.

### Syntax

```
var x = 5
```

Example:

```
var x = 5
print x
```

### Variables With Math Operations

Variables can store results of math expressions.

```
var x = 4 5 add
```

This assigns:

```
x = 9
```

Variables can also be used inside other expressions.

```
var x = 4 5 add
var y = x 10 add
```

Result:

```
y = 14
```

---

## Arithmetic Operations

Basic arithmetic operations are supported.

### Syntax

```
math number1 number2 operation
```

Example:

```
math 5 7 add
```

Supported operations:

- add
- sub
- mul
- div
- mod
- pow

---

## Multi-Number Math Operations

Operations can be applied to multiple numbers.

Example:

```
math 1 2 3 4 add
```

Result:

```
10
```

---

## Comparison Operations

Comparison operators return boolean values.

Example:

```
math 5 7 gt
```

Result:

```
False
```

Supported comparison operators:

- gt
- lt
- eq
- gte
- lte
- neq

---

## Stacks

Stacks allow storing and manipulating lists of values.

### Create Stack

```
stack nums [1,2,3]
```

### Stack Operations

Append value:

```
stack append nums 4
```

Pop value:

```
stack pop nums
```

Delete element by index:

```
stack del nums 1
```

---

## Loop Over Stack

You can iterate through stack values.

Example:

```
stack nums [1,2,3]

for x in nums
    print x
end
```

Output:

```
1
2
3
```

---

## For Loops

Loops can execute code multiple times.

Example:

```
var x = 3

for x
    print "loop"
end
```

Output:

```
loop
loop
loop
```

---

## If Statements

Conditional execution is supported.

### Syntax

```
if number1 number2 operator
    print "something"
end
```

Example:

```
if 6 7 lt
    print "6 is less than 7"
end
```

---

# Example Program

```
var x = 10
var y = 5

math x y add
print "done"
```

---

# Running the Interpreter

Run a program using:

```
python main.py program_name
```

Example:

```
python main.py program.my
```

---

# Future Improvements

Planned features include:

- while loops
- else blocks
- nested control structures
- REPL mode
- better error handling

---

# Purpose

This project was built to learn:

- interpreter design
- command parsing
- control flow execution
- operator dispatch tables
- simple language runtime implementation