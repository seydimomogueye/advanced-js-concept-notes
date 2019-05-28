## Inside the Engine

### Steps

---

1. Give a file into parser for lexical analysis. -> break the code into tokens
2. Tokens are given into AST (Abstract syntax tree) -> https://astexplorer.net/
3. pass AST to the interpreter to get byte code or to profiler who will pass it to compiler
4. Give code to the cpu.
