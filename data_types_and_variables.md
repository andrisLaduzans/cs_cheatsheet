# Data Types And Variables

## Console
```cs
Console.WriteLine(<arg>);
Console.ReadLine(); //read input from terminal
```

## Variables and Types
```cs
string foo = "Hello";
int x = 5;
double y = 420.69;
```

## Arithmetic Operators
```cs
int result; 
result = 10 + 5;  // 15
result = 10 - 5;  // 5
result = 10 * 5;  // 50
result = 10 / 5;  // 2
result = 10 % 5;  // 0
```

## Unary Operator
```cs
int a = 10;
a++; //11
```

## Math
```cs
double x = 81; 
double res = Math.Sqrt(x); //9

double pow_ab = Math.Pow(6, 2); //36
```
## .ToUpper()/.ToLower()
```cs
string str2 = "This is C# Program xsdd_$#%"; 
string upperstr2 = str2.ToUpper(); 
//"THIS IS C# PROGRAM XSDD_$#%"

string mixedCase = "This is a MIXED case string.";
string lower = mixedCase.ToLower();
//"this is a mixed case string."
```
## IndexOf()
```cs
string str = "Divyesh"; 
int index1 = str.IndexOf('s');
//5
```
## Bracket Notation
```cs
string value = "Dot Net Perls";
char first = value[0];
//D
char second = value[1];
//o
char last = value[value.Length - 1];
//s
```
## Substring()
Substring() is a string method used to retrieve part of a string while keeping the original data intact. The substring that you retrieve can be stored in a variable for use elsewhere in your program.
```cs
string myString = "Divyesh";
string test1 = myString.Substring(2);
```
## String Concatenation
```cs
string firstName = "Bruce";    
string lastName = "Vayne";    
string name = firstName + " " + lastName;    
//Bruce Vayne
```
## String Interpolation
```cs
int id = 100
string multipliedNumber = $"The multiplied ID is {id * 10}.";
//"The multiplied ID is 1000."
```