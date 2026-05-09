# SCCharts to Rust Compiler (`sctx_parser`)

This tool is a custom compiler that translates Sequentially Constructive Text (`.sctx`) files into executable Rust code.

## How the Pipeline Works
1. **Flex (`sctx.l`)**: Acts as the lexer. It reads your `.sctx` file character by character and groups them into recognized tokens.
2. **Bison (`sctx.y`)**: Acts as the parser. It takes the tokens from Flex, understands the structure of your state machine, and automatically generates the equivalent Rust code (structs, enums, and the `tick()` loop).
3. **GCC & Rustc**: GCC compiles the Flex and Bison C files into the actual parser executable (`sctx_parser`). Once the parser generates the `.rs` file, the Rust compiler (`rustc`) turns it into a final, runnable program.

## Prerequisites
Ensure you have the following installed on your Linux/Ubuntu system:
- `gcc` (GNU C Compiler)
- `flex` (Fast Lexical Analyzer)
- `bison` (GNU Parser Generator)
- `rustc` (Rust Compiler)

*(Installation on Ubuntu: `sudo apt install build-essential flex bison rustc`)*

## How to Build and Run the Project

**1. Build the Compiler**
To compile the Flex and Bison files into the `sctx_parser` executable, run:
```bash
make all
```
To compile and run the Rust file
```bash
make run
```
To clear the intermediate files before compilation
```bash
make clean
```
