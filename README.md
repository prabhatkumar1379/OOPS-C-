<div>
  <p><b>1</b>.What is an object in C#?</p>
</div>
<hr>
<p>
  An object is a real instance created in memory from a class. It holds data and can perform actions.
  <br>
  Note : Every object has its own identity, state, and behavior.
</p>
----------------------------------------------
<h1>Class(Blueprint)</h1>

```
class Employee
{
    public int Id;   //This is the STATE of the object Different objects can have different states.
    public string Name;  ////This is the STATE of the object Different objects can have different states.

    public void Work()
    {
        Console.WriteLine("Employee is working");
    }
}
```
