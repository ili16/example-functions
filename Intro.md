# Introduction

Welcome to my VSCode extension! This extension provides interfaces to use a prompt library with various programming languages.

Some of the key features of this extension include generating prompts with random instructions, displaying responses, allowing users to up- or downvote responses, and tracking the current prompt count. Additionally, users can retrieve either a random prompt or the highest-ranked prompt to further enhance their coding experience.

#### Task 0: enable the CodeLens feature by pressing Ctrl + Shift + P (opens command palette) and running the command "Modernizer VSCode: Enable CodeLens"

#### Task 1: Select the whole Function and generate an explanation prompt:

```Python
def add(a, b):
    return a + b
```

#### Task 2: Select the whole Function and retrieve the best response, Up- or Downvote it depending on the output:

```Java
public class HelloWorld 
{
    public static void main (String[] args)
    {
            System.out.println("Hello World!");
    }
}
```

#### Task 3: Select the whole Function and use a funny prompt from the pre-defined list

select -> right click -> Modernizer -> Generate Prompt By List -> funny

```Javascript
function multiply(a, b) {
    return a * b;
}
```

#### Task 4: Select the whole Function and generate a custom Prompt, then save it to your settings.json

```Golang
func add(a, b float64) float64 {
	return a + b
}
```
