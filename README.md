# llvm-pass-learn

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

    $ clang -flegacy-pass-manager -Xclang -load -Xclang build/badCalculator/libBadCalculatorPass.* a.cpp

<details>
  <summary>Example</summary>
  
  ```
❯ clang a.cpp
❯ ./a.out
❯ echo $?
6
❯ ./a.out a b c
❯ echo $?
9
❯ clang -flegacy-pass-manager -Xclang -load -Xclang build/badCalculator/libBadCalculatorPass.* a.cpp
HOHOHO Bad calculator
❯ ./a.out
❯ echo $?
5
❯ ./a.out a b c
❯ echo $?
20
  ```
</details>

## First operator

Logs the result of the first binary operation

<details>
  <summary>Example</summary>
  
  ```
❯ cc -c rtlib.c
❯ clang -flegacy-pass-manager -Xclang -load -Xclang build/firstOperator/libFirstOperatorPass.so -c a.cpp
❯ cc rtlib.o a.o -o exe
❯ ./exe
computed: 6
  ```
</details>

---

Skeleton to write the LLVM pass was picked up from -> https://github.com/sampsyo/llvm-pass-skeleton
