# Methods
## Optional Parameters
A parameter is optional if its declaration specifies a default argument.
```cs
static int AddSomeNumbers(int x, int y = 3, int z = 2)
{
  return x + y + z;
}

AddSomeNumbers(1); // Returns 6.
AddSomeNumbers(1, 1); // Returns 4.
AddSomeNumbers(3, 3, 3); // Returns 9.
```

## Out Parameters
`return` can only return one value. When multiple values are needed, out parameters can be used.
```cs
// f1, f2, and f3 are out parameters, so they must be prefixed with `out`.

static void GetFavoriteFoods(out string f1, out string f2, out string f3)
{
  // Notice how we are assigning values to the parameters instead of using `return`.
  f1 = "Sushi";
  f2 = "Pizza";
  f3 = "Hamburgers";
}

static void Main()
{
  string food1;
  string food2;
  string food3;

  // Variables passed to out parameters must also be prefixed with `out`.

  GetFavoriteFoods(out food1, out food2, out food3);
  
  // After the method call, food1 = "Sushi", food2 = "Pizza", and food3 = "Hamburgers".
  Console.WriteLine($"My top 3 favorite foods are {food1}, {food2}, and {food3}");
}
```

## Expression-Bodied Methods (Fat Arrow)
```cs
static int Add(int x, int y) {
  return x + y;
}

static void PrintUpper(string str) {
  Console.WriteLine(str.ToUpper());
}

// The same methods written in expression-body form.
static int Add(int x, int y) => x + y;
static void PrintUpper(string str) => Console.WriteLine(str.ToUpper());
```

## Lambda Expressions
```cs
int[] numbers = { 3, 10, 4, 6, 8 };

static bool isTen(int n) {
  return n == 10;
}

// `Array.Exists` calls the method passed in for every value in
`numbers` and returns true if any call returns true.
Array.Exists(numbers, isTen);

// using lambda expression
Array.Exists(numbers, (int n) => {
  return n == 10;
});

// Typical syntax
// (input-parameters) => { <statements> }
```

### Shorter Lambda Expressions
```cs
int[] numbers = { 7, 7, 7, 4, 7 };

Array.Find(numbers, (int n) => { return n != 7; });

// The type specifier on `n` can be inferred based
//on the array being passed in and the method body.
Array.Find(numbers, (n) => { return n != 7; });

// The parentheses can be removed since there is only one parameter.
Array.Find(numbers, n => { return n != 7; });

// Finally, we can apply the rules for expression-bodied methods.
Array.Find(numbers, n => n != 7);
```