# rv32emulator

## Building and running

Build using `make`

Run using `./obj/emulator [assembly file path]`

## Debugging commands

Execution will result in a command prompt, preceded by some information about the instruction to execute next.
For example:

```
Next: lui x02, 0x00000010
[inst:      1 pc:      0, src line    3] > 
```

The following are the supported commands:

* s, or [blank] : Step to the next instruction
* c : Continue execution until termination
* r : Reads the value of the registers. Both register number and alas formats can be used, without space after 'r'. e.g., `rx0`, `rra`. A simple `r` with no trailing register name will print all registers
* m : Reads memory values. Memory address prefixed with m (e.g., `m0x1000` or `m1024`) will print four bytes starting from that address. If you want to read more values, give the number of bytes as a parameger. e.g., `m0x1000 16`.
* b : Set breakpoint. e.g., `b17` to set a breakpoint at source code line 17. The list of existing breakpoints can be seen with a simple `b` with no suffixes. Breakpoints can be removed with an uppercase `B`. e.g., `B16`.

