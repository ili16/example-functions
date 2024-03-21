# semantic-similarity

Even though D.R.Y. is the one of the leading principles for any developer. Code will repeat itself between projects as they can't be accessed in the right context. Furthermore writing new code for a similar task which is already present in the codebase, should be written to the latest best practices which results in the same semantic function having multiple ways of being defined.

#### Task 1: For each of these functions: select the whole Function, right click and use the "Get similar Code" command:

```Golang
func FibonacciRecursion(n int) int {
    if n <= 1 {
        return n
    
    return FibonacciRecursion(n-1) + FibonacciRecursion(n-2)
}
```

```Javascript
private bool IsEven(int number) {
    if (number == 1) {
        return false;
    } else {
        return !IsEven(number - 1);
    }
}
```

```C#
List<int> numbers = new List<int>() { 1, 2, 3, 4, 5 };
for (int i = 0; i < numbers.Count; i++)
{
    Console.WriteLine(numbers[i]);
}
```