# Tungsten

A low-tech drawing program for working with lower resolution, limited-palette images. Tungsten is currently in-development and is being written in UxnTAL for the Uxn virtual computer. The expected release date for a usable version 1.0 is August 2022.

Tungsten is designed for devices with a minimum screen resolution of 256x192. Devices with smaller screens will still be able to run Tungsten, but the edges of the user interface might extend off the screen.


## Functionality

Tungsten is currently lacking many vital pieces of functionality, including the ability to load or save images from disk.


## Assembling

The program is one monolithic TAL source file, assembled with [`uxnasm` from 100r](https://git.sr.ht/~rabbits/uxn/).

The 100r assembler by default only allows 256 macro definitions in one program, but because Tungsten uses upwards of 400 macro definitions I've had to patch the assembler slightly to accomodate.

To raise the macro definition limit on your machine, go to the assembler source file `src/uxnasm.c` and change the line `Macro macros[0x100]` to `Macro macros[0x400]`, and the line
`if(p.mlen == 0x100)` to `if(p.mlen == 0x400)`. Recompile `uxnasm` and you'll be able to assemble Tungsten without errors.
