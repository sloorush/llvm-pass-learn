# logger-llvm-pass

A dummy LLVM pass to log the LLVM IR and get the functions, basic blocks, and instructions.
It's for LLVM 14.

Build:

    $ cd llvm-pass-skeleton
    $ mkdir build
    $ cd build
    $ cmake ..
    $ make
    $ cd ..

Run:

    $ clang -flegacy-pass-manager -Xclang -load -Xclang build/logger/libLoggerPass.* a.cpp

Skeleton to write the LLVM pass was picked up from -> https://github.com/sampsyo/llvm-pass-skeleton
