# Classes
```cs
using System;

namespace BasicClasses
{
  class Forest
  {
    public int age;

    public Forest(string name, string biome) {
      this.Name = name;
      this.Biome = biome;
      Trees = 10;
      ForestsCreated++;
    }
    
    public Forest(string name) : this(name, "Unknown"){ }
    
    public string Name { get; set; }
    public int Trees { get; private set; }
    
    public string Biome {
      get { return biome; }
      set {
        if (!value) {
          biome = "Unknown";
        } else {
          biome = value;
        }
      }
    }
         
    public int Grow() {
      Trees += 30;      
      return Trees;
    }

    public static int ForestsCreated { get; private set; }            
  }
}
```

### Constructor Override
Like methods, a constructor can be overloaded. It must have the same name as the enclosing class.
```cs
...
//Constructor w/ 2 arguments
public Forest(int area, string country)
{ 
  this.Area = area;
  this.Country = country;
}

// Constructor Override with one argument (declared in same class)
public Forest(int area)
{ 
  this.Area = area;
  this.Country = "Unknown";
}
...
```
### Parameterless Constructor
In C#, if no constructors are specified in a class, the compiler automatically creates a parameterless constructor.
```cs
public class Freshman
{
  public string FirstName { get; set; }
}

public static void Main (string[] args)
{
  Freshman f = new Freshman();
  string name = f.FirstName;
}
```

### Access Modifiers
`public` accessed from instance
`protected` accessed from subclass
`private` accessed form class

### Field
a field stores a piece of data within an object. It acts like a variable and may have a different value for each instance of a type.

A field can have a number of modifiers, including: public, private, static, and readonly. If no access modifier is provided, a field is private by default.
```cs
public class Person
{
   private string firstName;
   private string lastName;
}
```
### this Keyword
 the this keyword refers to the current instance of a class.
 ```cs
 // We can use the this keyword to refer to the current
 // class’s members hidden by similar names:
public NationalPark(int area, string state)
{
  this.area = area;
  this.state = state;
}

// The code below requires duplicate code,
// which can lead to extra work and errors when changes are needed:
public NationalPark(int area, string state)
{
  area = area;
  state = state;
}
public NationalPark(int area)
{
  area = area;
  state = "Unknown";
}

// Use this to have one constructor call another:
public NationalPark(int area) : this (state, "Unknown")
{ }
 ```

## Members
a class contains members, which define the kind of data stored in a class and the behaviors a class can perform.
```cs
class Forest
{
  public string name;
  public string Name
  {
    get { return name; }
    set { name = value; }
  }
}

// A member of a class can be a field (like name), a property (like Name)
// or a method (like get()/set()).
// It can also be any of the following:
// Constants
// Constructors
// Events
// Finalizers
// Indexers
// Operators
// Nested Types
 ```
## Dot Notation
```cs
//a member of a class can be accessed with dot notation.
string greeting = "hello";
Console.WriteLine(greeting.Length);

Math.Min(8, 920);
 ```

## Class Instance
 an object is an instance of a class. An object can be created from a class using the new keyword.
 ```cs
 Burger cheeseburger = new Burger();
 ```

## Property
a property is a member of an object that controls how one field may be accessed and/or modified.

A property defines two methods: a `get()` method that describes how a field can be accessed, and a `set()` method that describes how a field can be modified
```cs
...
public class Freshman
{
  private string firstName;

  public string FirstName
  {
    get { return firstName; }
    set { firstName = value; }
  }
}
...

...
public static void Main (string[] args) {
  Freshman f = new Freshman();
  f.FirstName = "Louie";
  
  // Prints "Louie"
  Console.WriteLine(f.FirstName);
}
...
 ```

## Property shorthand
an auto-implemented property reads and writes to a private field, like other properties, but it does not require explicit definitions for the accessor methods nor the field. It is used with the `{ get; set; }` syntax.
```cs
public class HotSauce
{
  public string Title { get; set; }

  public string Origin { get; set; }
}

...
public static void Main (string[] args) {
  HotSauce sauce = new HotSauce();
  sauce.Title = "Hot Sauce";
  
  Console.WriteLine(sauce.Title);
}
...
 ```

## Static Constructor
a static constructor is run once per type, not per instance. It must be parameterless. It is invoked before the type is instantiated or a static member is accessed.
```cs
class Forest
{
  static Forest()
  { 
    Console.WriteLine("Type Initialized"); 
  }
}
// In this class, either of the following two lines would trigger the
// static constructor (but it would not be triggered twice if these two 
// lines followed each other in succession):
Forest f  = new Forest();
Forest.Define();
 ```

## Static Class
a static class cannot be instantiated. Its members are accessed by the class name.

This is useful when you want a class that provides a set of tools, but doesn’t need to maintain any internal data.

Math is a commonly-used static class.
```cs
//Two examples of static classes calling static methods:
Math.Min(23, 97);
Console.WriteLine("Let's Go!");
 ```
