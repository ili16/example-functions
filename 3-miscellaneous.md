# Misc

These are just a collection of code snippets, if you want to explore more with the extension:

## Compiler Ambiguity:

int count = 0;
myfunction(++count, count);

## implicit Type Conversion:

#include <stdio.h>

int main() {
    int a = 300;
    char b = a;
    printf("%d\n", b); // Outputs unexpected value due to implicit Type conversion
    return 0;
}

## Concurrency:

package main

import (
    "fmt"
    "sync"
)

func concurrency() {
    var wg sync.WaitGroup
    for i := 0; i < 5; i++ {
        wg.Add(1)
        go func() {
            defer wg.Done()
            fmt.Println(i)
        }()
    }
    wg.Wait()
}