# Arrays and Loops
## Declaring Arrays
```cs
// Declare an array of length 8 without setting the values.
string[] stringArray = new string[8];

// Declare array and set its values to 3, 4, 5.
int[] intArray = new int[] { 3, 4, 5 };

// `numbers` and `animals` are both declared and initialized with values.
int[] numbers = { 1, 3, -10, 5, 8 };
string[] animals = { "shark", "bear", "dog", "raccoon" };
```

## Array Element Access
```cs
int[] numbers = { 3, 14, 59, 26, 53, 0 };

// Assign the last element, the 6th number in the array (currently 0), to 58.
numbers[5] = 58;

// Store the first element, 3, in the variable `first`.
int first = numbers[0];
```

### Array Length
```cs
int[] someArray = { 3, 4, 1, 6 };
Console.WriteLine(someArray.Length); // Prints 4
```

## For Loops
```cs
for (int i = 1; i <= 10; i++) {
  Console.WriteLine(i); 
}
```
## foreach Loop
```cs
string[] states = { "A", "A", "A", "A", "C", "C" };

foreach (string state in states) {
  Console.WriteLine(state);
}
```

## While Loop
while true or `break;`
```cs
string guess = "";

while (guess != "dog") {
  guess = Console.ReadLine();
}
```

## Do While Loop
```cs
do {
  DoStuff();
} while(boolCondition);

// This do-while is equivalent to the following while loop.

DoStuff();
while (boolCondition) {
  DoStuff();
}
```

## Jump Statements
`break`, `continue`, `return`
```cs
while (true) {
  // A `break` statement immediately terminates the loop that contains it.
  break;
}

for (int i = 1; i <= 10; i++) {
  if (i == 7) {
    // A `continue` statement skips the rest of the loop
    // and starts another iteration from the start.
    continue;
  }
  Console.WriteLine(i);
}

static int WeirdReturnOne() {
  while (true) {
    // Since `return` exits the method, the loop is also terminated.
    // Control returns to the method's caller.
    return 1;
  }
}
```