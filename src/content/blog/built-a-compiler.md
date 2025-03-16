---
title: Building SudoLang- A Hindi Inspired Programming Language
subtitle: how is a compiler working under the hood, learn by building your own programming language 
author: Arjit Sharma
courses: []
categories: ["Core-CS"]
image: /images/thumbnails/compiler.png
featured: true
draft: false
---

Programming languages are fascinating. But have you ever wondered **how they work under the hood?** As an academic exercise, I set out to build my own programming language **SudoLanguage**, a Hindi-inspired scripting language that transpiles to JavaScript!

> Disclaimer: I am not a subject expert in writing languages. I am just sharing my findings.
> 

## Features of SudoLang 🌟

SudoLang provides fundamental programming constructs, all with Hindi-inspired syntax:

✅ **Print Statements** – Display output using `CHAPO` (like `console.log`).

✅ **Variables & Assignment** – Declare variables with `MANLO`.

✅ **User Input** – Accept input using `PUCHO`.

✅ **Arithmetic Expressions** – Perform calculations with `+`, `-`, `*`, `/`.

✅ **Conditional Statements** – Use `AGAR` (if) with `{}` blocks.

✅ **Loops** – Use `JABTAK` (while) for iterations.

✅ **Comments** – Add comments with `#`.

## Example Code in SudoLang

```javascript
MANLO x = 5;
CHAPO x;

PUCHO y;
CHAPO y;

AGAR (x > 3) {
    CHAPO "X bada hai!";
}

JABTAK (x < 10) {
    CHAPO x;
    MANLO x = x + 1;
}

# This is a comment
```

### Output 
```bash
5
10 ---> Entered by user
X bada hai
5
6
7
8
9
10

```


## Installation & Running

You can install SudoLang globally using npm:

```bash
npm install -g sudolang
```

Then, run a `.hindi` script like this:

```bash
hindic myscript.hindi
```

## How it works ? (The Broader Picture)

1. **Lexer (Tokenizer)** – Reads the source code **character by character** and converts it into **tokens**, the smallest building blocks of the language.
2. **Parser** – Processes these tokens, checks if they follow the correct syntax, and structures them into a **parse tree** for execution.
3. **Emitter** – Converts Intermediatory code into low level code, making it executable.

## Understanding the Grammar (BNF-like)

SudoLang follows a **BNF-like grammar** (Backus-Naur Form) to define its syntax. Here’s a simplified structure:

```bash
<program> ::= <statement_list>

<statement_list> ::= <statement> <newline> <statement_list>
                   | <statement> <newline>
                   | ε   (* Empty Line Allowed *)

<statement> ::= <assignment>
              | <print_statement>
              | <input_statement>
              | <if_statement>
              | <while_loop>

<assignment> ::= "MANLO" <identifier> "=" <expression> ";"

<print_statement> ::= "CHAPO" <expression> ";"

<input_statement> ::= "PUCHO" <identifier> ";"

<if_statement> ::= "AGAR" "(" <condition> ")" "{" <statement_list> "}"

<while_loop> ::= "JABTAK" "(" <condition> ")" "{" <statement_list> "}"

```

SudoLang follows a **recursive descent parsing** approach and supports **LL(1) parsing**, meaning it looks at only one token at a time without backtracking.

## Understanding Code Flow  🚀

Here’s a breakdown of how the **different components** of SudoLang work together:

1. **package.json** - Defines the project, dependencies (`readline-sync`), and command-line executable (`hindic`).
2. **bin/hindic** -
    - Reads the `.hindi` source file.
    - Passes the code through **Lexer** (tokenizes), **Parser** (checks syntax & builds structure), and **Emitter** (transpiles to JavaScript).
    - Writes the JavaScript output to `temp.js`.
    - Runs the generated JavaScript using Node.js.
    - Deletes `temp.js` after execution.
3. **src/lexer** - 
    - **Scans the source code** character by character.
    - Groups them into **tokens**, which are later used by the Parser.
    - Creates `Token` objects, storing both the text (actual code) and type.
4. **src/emitter** -
    - Stores transpiled code in `this.code`.
    - Writes the final JavaScript output to a file.
5. **src/parser -** 
    - Reads tokens sequentially using `nextToken()`.
    - Matches tokens to **grammar rules** (like `if`, `while`, `let`).
    - Uses a **recursive descent approach** to parse expressions, conditions, and loops.
    - Generates JavaScript code by sending parsed structures to the **Emitter**.

## Deeper Dive: What’s Next?

Right now, SudoLang is a **transpiler** (converts one high-level language to another). But if we wanted to build a **true compiler** that generates machine code, we could explore:

 

1. **LLVM (Low-Level Virtual Machine)** - A compiler framework that generates optimized machine code for multiple architectures.

```css
Sudolanguage → Lexer → Parser → LLVM IR → Machine Code (x86, ARM, etc.)
```

2. **Direct Assembly Code Generation** - Emit **x86 assembly** and use an **assembler** (like `nasm`) to generate machine code.

3. **WebAssembly (WASM)** – A low-level binary format that runs on modern browsers.

## Conclusion: Seeing the Matrix 👀

I’d **100% recommend** building your own compiler (even if it’s just a transpiler). It fundamentally changes how you see code.

Beyond learning about **lexing, parsing, and ASTs**, you gain something even more valuable:

1. **Programming is Abstraction**

A high-level language is just a bunch of strings that the compiler accepts. The compiler dictates the language - it breaks it down, checks validity, and converts it to low-level code. Then the cycle repeats until we reach machine instructions.

2. **Errors? They Excite Me Now.**

In sudoLang, I didn’t even bother giving useful message. Debugging feels less like a headache and more like a feature. Wow, atleast the language tells me where mistake might be !

3. **The Better You Understand Your Language, The Better You Write.**

Compilers don’t “think”–they **follow rules**. The more you understand **how they optimize (or struggle)**, the better you can write better code.

Now, every time I write code, I ask myself:

🤔 What’s the **compiler doing**?

🤔 How is it **parsing this statement**?

🤔 How does this turn into **machine instructions**?