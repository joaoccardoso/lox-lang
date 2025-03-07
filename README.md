# Lox Language Implementation

This is an implementation in python of the Lox Language, a basic programming language described in the book [Crafiting Interpreters](https://craftinginterpreters.com/).

## Usage 

```shell
# Create new venv (for runing the tests)
$ python3 -m venv venv

# Running the REPL
$ python3 main.py

# Running a .lox script
$ python3 main.py <path/to/script.lox>
```

## Lox Language Grammar Rules

```
expression -> equality;
equality   -> comparison (("!=" | "==") | comparison)*
comparison -> term ((">" | "<" | ">=" | "<=") | term)*
term       -> factor (("+" | "-") | factor)*
factor     -> unary (("*" | "/") | unary)*
unary      -> ("!" | "-") unary | primary;
primary    -> NUMBER | STRING | "true" | "false" | "nil" | "(" expression ")";
```

```shell
# AST can be recreated with:
$ python tools/ast_generator.py ./lox
```

## Script Example

```csharp
var str = "lox";
var number = 1234.67;

fun do_something(a, b) {
    return a * b;
}

print do_something(number, 2);
print str;
```

## Tests

```shell
$ pytest
```