# LINQ
LINQ is a set of language and framework features for writing queries on collection types. It is useful for selecting, accessing, and transforming data in a dataset.
LINQ features can be used in a C# program by importing the System.Linq namespace.
```cs
using System.Linq;
 ```
 
 ## var
 Since the type of an executed LINQ query’s result is not always known, it is common to store the result in an implicitly typed variable using the keyword var.
 ```cs
 var custQuery = from cust in customers
                where cust.City == "Phoenix"
                select new { cust.Name, cust.Phone };
 ```

 ## Method & Query Syntax
 LINQ queries can be written in method syntax or query syntax.

Method syntax resembles most other C# method calls, while query syntax resembles SQL.
```cs
// Method syntax
var custQuery2 = customers.Where(cust => cust.City == "London");

// Query syntax
var custQuery =  
    from cust in customers  
    where cust.City == "London"  
    select cust;
 ```

## Where
In LINQ queries, the Where operator is used to select certain elements from a sequence.

It expects an expression that evaluates to a boolean value.
Every element satisfying the condition will be included in the resulting query.
It can be used in both method syntax and query syntax.
```cs
List<Customer> customers = new List<Customer>
{
  new Customer("Bartleby", "London"),
  new Customer("Benjamin", "Philadelphia"),
  new Customer("Michelle", "Busan" )
};

// Query syntax
var custQuery =  
    from cust in customers  
    where cust.City == "London"  
    select cust;

// Method syntax
var custQuery2 = customers.Where(cust => cust.City == "London");

// Result: Customer("Bartleby", "London")
 ```

## From
In LINQ queries, the from operator declares a range variable that is used to traverse the sequence. It is only used in query syntax.
```cs
string[] names = { "Hansel", "Gretel", "Helga", "Gus" };

var query =
  from n in names
  where n.Contains("a")
  select n;

// Result: Hansel, Helga
 ```
## Select
In LINQ queries, the Select operator determines what is returned for each element in the resulting query. It can be used in both method and query syntax.
```cs
string[] trees = { "Elm", "Banyon", "Rubber" };

// Query syntax
var treeQuery =
  from t in trees
  select t.ToUpper();

// Method syntax
var treeQuery2 = names.Select(t => t.ToUpper());

// Result: ELM, BANYON, RUBBER
 ```

## LINQ & foreach
You can use a foreach loop to iterate over the result of an executed LINQ query.
```cs
string[] names = { "Hansel", "Gretel", "Helga", "Gus" };

var query = names.Where(n => n.Contains("a"));
  
foreach (var name in query)
{
  Console.WriteLine(name);
}
 ```

 ## Count()
 The result of an executed LINQ query has a method Count(), which returns the number of elements it contains.
 ```cs
 string[] names = { "Hansel", "Gretel", "Helga", "Gus" };

var query = names.Where(x => x.Contains("a"));

Console.WriteLine(query.Count());
// Output: 2
 ```
