# logger-llvm-pass

A dummy LLVM pass collection made to learn.
It's for LLVM 14.

Build:

    $ cd llvm-pass-skeleton
    $ mkdir build
    $ cd build
    $ cmake ..
    $ make
    $ cd ..

## Logger Pass

A dummy LLVM pass to log the LLVM IR and get the functions, basic blocks, and instructions.

Run:

    $ clang -flegacy-pass-manager -Xclang -load -Xclang build/logger/libLoggerPass.* a.cpp

## BadCalculator Pass

A bad calculator that changes you first addition to multiplication

Run:

    $ clang -flegacy-pass-manager -Xclang -load -Xclang build/badCalculator/libBadCalculatorPass.* a.cp

Skeleton to write the LLVM pass was picked up from -> https://github.com/sampsyo/llvm-pass-skeleton
