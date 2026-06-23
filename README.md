# Mini Interpreter

A line-by-line interpreter for a custom scripting language, written from scratch in Python. Built as part of MIT 6.100L to learn how interpreters work at a low level, without relying on any parsing libraries or external dependencies.

The language uses **postfix (Reverse Polish Notation)** for expressions and supports variables, stacks, arithmetic, comparisons, and control flow.

---

## Design Highlights

- **Operator dispatch tables** — arithmetic and comparison operations are resolved through dictionaries mapping keyword strings to Python callables, avoiding long chains of conditionals
- **Dual variable environments** — scalar values and stack structures are tracked in separate dictionaries, allowing independent lookup and mutation
- **Block-based control flow** — for loops and conditionals extract their body as a sub-list of lines and execute them as a nested program, enabling clean separation between parsing and execution
- **Postfix evaluation** — expressions like `4 5 add` are evaluated left-to-right with the operator as the final token, keeping the parser simple and uniform

---

## Language Reference

### Print

```
print "Hello, World"
print x
```

Prints a string literal or a variable's current value.

---

### Variables

```
var x = 5
var name = "Alice"
```

Variables hold numbers or strings. Numbers are stored as floats internally and displayed as integers when the result is whole.

#### Variables with expressions

```
var x = 4 5 add
var y = x 10 sub
```

Expressions use postfix notation: operands come first, operator last. Variable names are resolved at evaluation time.

---

### Arithmetic

```
math 5 7 add
math 1 2 3 4 add
```

Operations are applied left-to-right across all operands, supporting chains of more than two numbers.

| Operation      | Keyword |
|----------------|---------|
| Addition       | add     |
| Subtraction    | sub     |
| Multiplication | mul     |
| Division       | div     |
| Modulo         | mod     |
| Exponentiation | pow     |

---

### Comparisons

```
math 5 7 gt
```

Returns `True` or `False`.

| Comparison            | Keyword |
|-----------------------|---------|
| Greater than          | gt      |
| Less than             | lt      |
| Equal                 | eq      |
| Greater than or equal | gte     |
| Less than or equal    | lte     |
| Not equal             | neq     |

---

### Stacks

```
stack nums [1,2,3]
stack append nums 4
stack pop nums
stack del nums 1
```

Stacks are ordered lists of values. Operations: append, pop (removes last), del (removes by index).

---

### For Loop (count-based)

```
var n = 3

for n
    print "hello"
end
```

Executes the enclosed block `n` times.

---

### For Loop (stack iteration)

```
stack fruits [apple,banana,cherry]

for item in fruits
    print item
end
```

Iterates over each element in a stack, binding the current element to the loop variable per iteration.

---

### If Statement

```
if 6 7 lt
    print "6 is less than 7"
end
```

Evaluates the comparison and executes the block only if it holds.

---

## Example Program

```
var x = 10
var y = 3

var sum = x y add
var remainder = x y mod

print sum
print remainder
```

Output:

```
13
1
```

---

## Getting Started

### Requirements

Python 3.x. No external dependencies.

### Run

```bash
python main.py examples/program.my
```

### Included Examples

| File              | What it shows                        |
|-------------------|--------------------------------------|
| program.my        | Variables and arithmetic             |
| for.my            | Count-based loop                     |
| for_on_stacks.my  | Iterating over a stack               |
| stack.my          | Stack creation and operations        |
| if.my             | Conditional execution                |

---

## Project Structure

```
.
├── main.py            # Tokenizer, dispatcher, and execution loop
├── README.md
├── LICENSE
└── examples/
    ├── program.my
    ├── for.my
    ├── for_on_stacks.my
    ├── stack.my
    └── if.my
```

---

## Concepts Implemented

Built without any parsing libraries to understand how interpreters work under the hood.

- Line-by-line tokenization and execution
- Dispatch tables for operation resolution
- Dual variable environments for scalars and lists
- Block extraction and re-execution for loops and conditionals
- Postfix expression evaluation with multi-operand chaining
- Stack as a first-class data structure with named operations