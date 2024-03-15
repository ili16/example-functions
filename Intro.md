# Introduction

Welcome to my VSCode extension! This extension provides interfaces to use a prompt library with various programming languages.

Some of the key features of this extension include generating prompts with random instructions, displaying responses, allowing users to up- or downvote responses, and tracking the current prompt count. Additionally, users can retrieve either a random prompt or the highest-ranked prompt to further enhance their coding experience.

#### Task 0: enable the CodeLens feature by pressing Ctrl + Shift + P (opens command palette) and running the command "Modernizer VSCode: Enable CodeLens"

## Python

#### Task 1: Select the whole Function and generate an explanation prompt:

```
def add(a, b):
    return a + b
```

## Java

#### Task 2: Select the whole Function and retrieve the best response, Up- or Downvote it depending on the output:

```Java
public class ArithmeticFunctions {
    public static double divide(double a, double b) {
        if (b == 0) {
            throw new ArithmeticException("Cannot divide by zero");
        }
        return a / b;
    }
}
```

## Javascript

```
function multiply(a, b) {
    return a * b;
}
```

## Golang

```
func add(a, b float64) float64 {
	return a + b
}
```

func AddTwoNumbers(a int, b int) int {
    return a + b
}

func AddThreeNumbers(a int, b int, c int) int {
    return a + b + c
}

func AddTwoNumbers(a int, b int) int {
    return b + a
}