# Arbitrary Precision Calculator (APC)

A command-line calculator written in **C** that performs arithmetic on numbers of **any length**, far beyond the range of built-in types like `int`, `long long` or `double`.

Numbers are stored digit by digit in linked lists, and each operation is implemented manually (the way you'd do it on paper), so there is no overflow and no fixed upper limit other than available memory.

---

## Features

- Addition (`+`)
- Subtraction (`-`)
- Multiplication (`x`)
- Division (`/`)
- Works with very large operands (hundreds or thousands of digits)
- Modular code: one source file per operation
- Simple `makefile` build

---

## Project Structure

```
.
├── APC_header.h      # Structure definitions, macros and function prototypes
├── calculator.c      # main(): argument validation, operator selection, output
├── inserting_fun.c   # Converts input strings into digit lists (insert functions)
├── add_fun.c         # Addition logic
├── sub_fun.c         # Subtraction logic
├── mul_fun.c         # Multiplication logic
├── division_fun.c    # Division logic
├── makefile          # Build script
└── README.md
```

---

## How It Works

1. The two operands and the operator are read from the command line.
2. Each operand is validated and converted into a linked list, with one digit per node.
3. The chosen operation walks through the lists digit by digit, handling carry and borrow manually.
4. The result is stored in a third list and printed.

---

## Getting Started

### Prerequisites

- GCC (or any C compiler)
- `make`
- Linux, macOS, or Windows with MinGW/WSL

### Build

```bash
git clone https://github.com/narendra8010/APC---Arbitrary-Precision-Calculator.git
cd APC---Arbitrary-Precision-Calculator
make
```

Or compile manually:

```bash
gcc calculator.c inserting_fun.c add_fun.c sub_fun.c mul_fun.c division_fun.c -o result.exe
```

### Run

```bash
./result.exe <operand1> <operator> <operand2>
```

---

## Usage Examples

```bash
# Addition
./result.exe 99999999999999999999 + 1

# Subtraction
./result.exe 100000000000000000000 - 1

# Multiplication (use quotes or x to avoid shell wildcard expansion)
./result.exe 123456789123456789 x 987654321987654321

# Division
./result.exe 100000000000000000000 / 25
```

> Note: `*` is expanded by the shell, so use `x` or `"*"` for multiplication.

---

## Concepts Used

- Linked lists (dynamic memory allocation)
- Pointers and structures
- String-to-list conversion
- Manual carry/borrow arithmetic
- Multi-file C projects and header files
- Makefiles

---

## Possible Improvements

- Support for negative numbers and decimals
- Modulus and power operations
- Interactive mode
- Input validation with clearer error messages
- Unit tests

---

## Author

**Narendra**
GitHub: [@narendra8010](https://github.com/narendra8010)

---

## License

This project is open source and available for learning and educational use.
