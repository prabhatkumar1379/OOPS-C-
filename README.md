
<details>
  <summary><b>❓ What is an object in C#?</b></summary>

  <p>
    An object is a <b>real instance created in memory from a class</b>.  
    It holds data and can perform actions.
  </p>

  <p>
    <b>Note:</b> Every object has its own <b>identity</b>, <b>state</b>, and <b>behavior</b>.
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
**Note:** emp and emp2 are objects created from the same class, each having its own identity and state, while sharing the same behavior defined in the class.

<details>
  <summary><b>❓ What is the difference between a class and an object?</b></summary>

  <p>
    A <b>class</b> is a blueprint or template, while an <b>object</b> is a real instance created from that class.
  </p>

  <p>
    A class does not occupy memory for data, but an object occupies memory.
  </p>
</details>

<details>
  <summary><b>❓ Can we create multiple objects from the same class?</b></summary>

  <p>
    Yes, we can create multiple objects from the same class.
    Each object will have its <b>own identity</b> and <b>separate state</b>,
    but all objects share the same <b>behavior</b> defined in the class.
  </p>
</details>

<details>
  <summary><b>❓ What happens when an object is created in C#?</b></summary>

  <p>
    When an object is created:
  </p>

  <ul>
    <li>Memory is allocated for the object</li>
    <li>The constructor (if present) is executed</li>
    <li>The object becomes ready to use</li>
  </ul>
</details>

<details>
  <summary><b>❓ Where does an object live in memory?</b></summary>

  <p>
    In C#, objects are created on the <b>Heap</b>.
    The reference variable (like <code>emp</code>) is stored on the <b>Stack</b>.
  </p>

```

STACK                           HEAP
-----                           ------------------
emp  ──────────────┐            Employee Object #1
                    └────────▶  Id = 101
                                 Name = "Prabhat Yadav"
                                 Work()

emp2 ─────────────┐             Employee Object #2
                   └─────────▶  Id = 2
                                 Name = "Pushpa Yadav"
                                 Work()
```
</details>

<details>
  <summary><b>❓ Does every object have its own copy of data?</b></summary>

  <p>
    Yes, every object has its own copy of instance variables.
    Changing the state of one object does not affect another object.
  </p>
</details>

<details>
  <summary><b>❓ Can an object exist without a class in C#?</b></summary>

  <p>
    No. In C#, every object must be created from a class.
    A class defines the structure and behavior required to create an object.
  </p>
</details>

<details>
  <summary><b>❓ How is object identity determined in C#?</b></summary>

  <p>
    Object identity is determined by its reference.
    Even if two objects have the same data, they are different objects
    if they are stored at different memory locations.
  </p>
</details>

<details>
  <summary><b>📝 MCQ 1: What is an object in C#?</b></summary>

  <p>A. A blueprint of a class</p>
  <p>B. A real instance created from a class</p>
  <p>C. A method inside a class</p>
  <p>D. A namespace</p>

   <details>

  <p><b>✅ Correct Answer:</b> B</p>
  <p>
    An object is a real instance created in memory from a class.
  </p>
   </details>
    
</details>

<details>
  <summary><b>🔴 MCQ 1: Two objects have the same values but different references. Are they the same object?</b></summary>
<br>
  <p>A. Yes, because data is same</p>
  <p>B. Yes, if they are of same class</p>
  <p>C. No, they are different objects</p>
  <p>D. Depends on compiler optimization</p>

  <hr/>
  <details>
     <p><b>✅ Correct Answer:</b> C</p>
  <p>
    Objects are identified by their reference (memory location).
    Even if data is identical, different references mean different objects.
  </p>
  </details>
  
</details>

<details>
  <summary><b>🔴 MCQ 2: What happens after assigning one object reference to another?</b></summary>

  <pre>
Employee emp1 = new Employee();
Employee emp2 = emp1;
emp2.Name = "Changed";
  </pre>

  <p>A. emp1.Name is unchanged</p>
  <p>B. emp2 points to a new object</p>
  <p>C. emp1.Name also becomes "Changed"</p>
  <p>D. Compilation error</p>

  <details>

  <p><b>✅ Correct Answer:</b> C</p>
  <p>
    Both <code>emp1</code> and <code>emp2</code> point to the same object in memory.
    Changing through one reference affects the same object.
  </p>
  
  </details>
</details>

<details>
  <summary><b>🔴 MCQ 4: When does an object become eligible for garbage collection?</b></summary>

  <p>A. When method execution ends</p>
  <p>B. When reference goes out of scope</p>
  <p>C. When no references point to the object</p>
  <p>D. When Dispose() is called</p>

<details>
    <hr/>

  <p><b>✅ Correct Answer:</b> C</p>
  <p>
    An object becomes eligible for GC only when there are no active references pointing to it.
    Garbage collection timing is non-deterministic.
  </p>
</details>
</details>

<details>
  <summary><b>🔴 MCQ 5: Can an object exist without any reference?</b></summary>

  <p>A. Yes, permanently</p>
  <p>B. Yes, until GC runs</p>
  <p>C. No, object is destroyed immediately</p>
  <p>D. Only for value types</p>

<details>

  <hr/>

  <p><b>✅ Correct Answer:</b> B</p>
  <p>
    An object can exist temporarily without references.
    It will be removed later by the Garbage Collector.
  </p>
  
</details>

<details>
  
  <summary><b>🔴 MCQ 6: What happens immediately after object memory allocation?</b></summary>

  <p>A. Methods are executed</p>
  <p>B. Fields are initialized</p>
  <p>C. Constructor is executed</p>
  <p>D. Finalizer is executed</p>

<details>

  <p><b>✅ Correct Answer:</b> C</p>
  <p>
    After memory allocation, the constructor is executed to initialize the object.
  </p>
  
</details>

</details>


</details>


<details>
  
  <summary><b>🔴 MCQ 7: How are objects passed to methods in C#?</b></summary>

  <p>A. By value</p>
  <p>B. By reference</p>
  <p>C. By value of reference</p>
  <p>D. By pointer</p>
  
 <details>
   
          <p><b>✅ Correct Answer:</b> C</p>
          <p>
            C# passes object references by value.
            The reference is copied, not the object itself.
          </p>
          
 </details>
      
</details>

<details>
  
  <summary><b>🔴 MCQ 8: What does '==' compare for reference types by default?</b></summary>

  <p>A. Object data</p>
  <p>B. Object state</p>
  <p>C. Reference (memory address)</p>
  <p>D. HashCode</p>

    <details>

        <p><b>✅ Correct Answer:</b> C</p>
        <p>
          For reference types, <code>==</code> compares references unless overloaded.
        </p>
    </details>
    
</details>

<details>
  <summary><b>🔴 MCQ 9: What kind of copy happens when assigning one object to another?</b></summary>

  <p>A. Deep copy</p>
  <p>B. Shallow copy</p>
  <p>C. Clone copy</p>
  <p>D. Memory duplication</p>

  <details> 

      <p><b>✅ Correct Answer:</b> B</p>
      <p>
        Assignment copies the reference, not the actual object.
        This is a shallow copy behavior.
      </p>
  
  </details>
  
</details>

<details>
  
  <summary><b>🔴 MCQ 10: Is object destruction deterministic in C#?</b></summary>

  <p>A. Yes, always</p>
  <p>B. Yes, when Dispose() is called</p>
  <p>C. No, it depends on GC</p>
  <p>D. Only for large objects</p>

  <details>

 

  <p><b>✅ Correct Answer:</b> C</p>
  <p>
    Garbage collection is non-deterministic.
    Object destruction timing cannot be predicted.
  </p>
  
  </details>
  
</details>







</details>
