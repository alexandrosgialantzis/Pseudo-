# Pseudo IDE

Pseudo IDE is a web tool to write, read, and run code written in the Pseudo programming language.

## Code Structure

The project is built with Angular and splits into three main parts.

### 1. Tokenizing
The Lexer reads raw input text character by character. It turns words, numbers, and symbols into simple tokens. The Position Tracker monitors line and column numbers to pinpoint errors.

### 2. Parsing
The Parser takes the tokens and builds an Abstract Syntax Tree (AST). It uses grammar rules to check if the code structure is correct. Each node in the tree represents an action, such as a variable assignment, loop, or math operation.

### 3. Execution
The Interpreter walks through the AST nodes one by one to run the code.
- Data Types: Handles numbers, strings, lists, and functions.
- Symbol Table: Stores variables and function definitions in memory while the code runs.
- Context: Keeps track of current execution environments and parent scopes.

## User Interface

- Code Editor: A text area where users type Pseudo code.
- Run Button: Triggers the interpreter service.
- Output Console: Displays standard output messages or runtime errors.

## How to Run

1. Install dependencies: npm install
2. Start the local server: ng serve
3. Open a browser and navigate to http://localhost:4200
4. 
