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
using System;

namespace DemoObject
{
    class Employee
    {
        // ---------------- STATE ----------------
        // Id represents the STATE (data) of the object
        public int Id;

        // Name also represents the STATE of the object
        public string Name;

        // ---------------- BEHAVIOR ----------------
        // Work() represents the BEHAVIOR of the object
        // The object performs an action using its current state
        public void Work()
        {
            Console.WriteLine($"Employee with Name: {Name} and Id: {Id} is working");
        }

        public static void Main()
        {
            // ---------------- OBJECT 1 ----------------
            // emp is an OBJECT (real instance) created in memory from Employee class
            // emp is the IDENTITY of the object
            Employee emp = new Employee();

            // Setting STATE of object emp
            emp.Id = 101;
            emp.Name = "Prabhat Yadav";

            // Calling BEHAVIOR using the object
            emp.Work();

            // ---------------- OBJECT 2 ----------------
            // emp2 is another OBJECT created from the same class
            // Same class, but different IDENTITY and separate memory
            Employee emp2 = new Employee();

            // Setting a different STATE for emp2
            emp2.Id = 2;
            emp2.Name = "Pushpa Yadav";

            // emp2 performs the same behavior, but result differs due to different STATE
            emp2.Work();

            // ✅ This proves:
            // - Same class
            // - Multiple objects
            // - Different identity
            // - Different state
            // - Same behavior
        }
    }
}

```
