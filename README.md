# C-like Language Interpreter

## Table of Contents
1. [Introduction](#introduction)
2. [About the Language](#about-the-language)
3. [Features](#features)
4. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Installation](#installation)
5. [Usage](#usage)
6. [Language Syntax](#language-syntax)
7. [Examples](#examples)
8. [Project Structure](#project-structure)
9. [Testing](#testing)
10. [Contributing](#contributing)
11. [License](#license)
12. [Acknowledgments](#acknowledgments)

## Introduction

This project is an implementation of an interpreter of the C-like programming language, Monkey, written in Go. The language is designed for educational purposes to demonstrate the principles of interpreter design and implementation.

## About the Language

Our C-like language is a simple, dynamically-typed language that supports:

- C-like syntax
- Variable bindings
- Multiple data types (integers, booleans, strings)
- Arithmetic expressions
- Built-in functions
- First-class and higher-order functions
- Closures
- Array data structure
- Hash/Dictionary data structure

While this language is not intended for production use, it serves as an excellent tool for learning about language design, parsing, and interpretation.

## Features

- **Lexer**: Transforms source code into tokens
- **Parser**: Constructs an Abstract Syntax Tree (AST) from tokens
- **Evaluator**: Interprets the AST and executes the program
- **REPL (Read-Eval-Print Loop)**: Interactive mode for testing code
- **Error Handling**: Provides informative error messages for syntax and runtime errors

## Getting Started

### Prerequisites

- Go (version 1.16 or later recommended)
- Git

### Installation

1. Clone the repository:
   ```
   git clone https://github.com/jeorozc0/monkey-interpreter.git
   ```
2. Navigate to the project directory:
   ```
   cd monkey-interpreter
   ```
3. Build the project:
   ```
   go build
   ```

## Usage

To start the REPL:

```
./monkey_interpreter
```

This will open an interactive prompt where you can enter code.

To run a script file:

```
./monkey_interpreter path/to/your/script.cl
```

## Language Syntax

Here's a brief overview of the language syntax:

- **Variable Binding**:
  ```
  let x = 5;
  let y = 10;
  let foobar = add(x, y);
  ```

- **Functions**:
  ```
  let add = fn(a, b) { return a + b; };
  ```

- **Conditionals**:
  ```
  if (x > y) {
    return x;
  } else {
    return y;
  }
  ```

- **Arrays**:
  ```
  let myArray = [1, 2, 3, 4, 5];
  ```

- **Hashes/Dictionaries**:
  ```
  let myHash = {"name": "John", "age": 30};
  ```

## Examples

Here are some example programs:

1. Fibonacci sequence:
   ```
   let fibonacci = fn(x) {
     if (x == 0) {
       0
     } else {
       if (x == 1) {
         return 1;
       } else {
         fibonacci(x - 1) + fibonacci(x - 2);
       }
     }
   };
   ```

2. Map function:
   ```
   let map = fn(arr, f) {
     let iter = fn(arr, accumulated) {
       if (len(arr) == 0) {
         accumulated
       } else {
         iter(rest(arr), push(accumulated, f(first(arr))));
       }
     };
     iter(arr, []);
   };
   ```

## Project Structure

- `lexer/`: Contains the lexical analyzer
- `parser/`: Implements the parser for creating the AST
- `ast/`: Defines the Abstract Syntax Tree structures
- `evaluator/`: Contains the interpreter logic
- `object/`: Defines object system for the language
- `repl/`: Implements the Read-Eval-Print Loop
- `token/`: Defines token types and structures

## Testing

To run the test suite:

```
go test ./...
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments
- Thorsten Ball, author of "Writing an Interpreter in Go"
- The Go programming language team
- All contributors and supporters of this project
