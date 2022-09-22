# Logic and Conditionals
## Boolean Expressions
```cs
bool a = (2 > 1);
bool b = a && true;
bool c = !false || (7 < 8);
```
## Logical Operators
```cs
// These variables equal true.
bool a = true && true;
bool b = false || true;
bool c = !false;

// These variables equal false.
bool d = true && false;
bool e = false || false;
bool f = !true;
```
## Comparison Operators
```cs
int x = 5;
Console.WriteLine(x < 6); // "True"
Console.WriteLine(x > 8); // "False"

string foo = "foo";
Console.WriteLine(foo == "bar"); //"False"
```

## If Statements
```cs
if (true) {
  // This code is executed.
}
```

## Switch Statements
in c# switch statements are not self closing on case match
```cs
switch (color) {
  case "red":
    //do something
    break;
  case "blue":
    //do something else
    break;
  default:
    //do default
    break;
}
```

## Ternary Operator
`condition ? expression1 : expression2`

## If and Else If
```cs
int x = 100, y = 80;
 
if (x > y)
{
  Console.WriteLine("x is greater than y");
} 
else if (x < y) 
{
  Console.WriteLine("x is less than y");
} 
else
{
  Console.WriteLine("x is equal to y");
}
```


