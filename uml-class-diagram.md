# UML Class Diagram

It’s like a blueprint or map of your code — drawn out visually.
It shows you what classes your system has, what they contain, and how they’re connected.

#### **4 Things It Shows**

1. Classes → The main building blocks (like Student, Car, Bank)
2. Attributes → What each class knows (like name, age, balance)
3. Operations → What each class can do (like drive(), withdraw())
4. Relationships → How classes talk to or depend on each other (like "A student ENROLLS in a course")


#### **What is a Class?**

Think of a Class as a Blueprint or Template. It defines what an object should look like and what it can do.

But it’s not the object itself—just the idea or plan.

example : basic Dog example
```
class Dog {
  constructor(name, color, breed) {
    // ** Attributes (State) **
    this.name = name;
    this.color = color;
    this.breed = breed;
  }

  // ** Methods ** 
  bark() {
    console.log("Woof!");
  }

  eat() {
    console.log("Nom nom nom");
  }
}

// create an object
const myDog = new Dog("Bruno", "Brown", "Labrador");
myDog.bark(); // Woof!

```

#### **UML Class Notation**

UML Class Notation is the way we visually represent a class in a UML (Unified Modeling Language) class diagram. It shows, the class name, It's attributes (variables/state) and It's operations (methods/behavior).

Basic UML Class Box Structure

A UML class is represented as a rectangle divided into three compartments.
```
---------------------------
|       Class Name        |   ← Top section (Name)
---------------------------
|   Attributes (Variables)|   ← Middle section (State)
---------------------------
|   Operations (Methods)  |   ← Bottom section (Behavior)
---------------------------
```

Class Name : Appears at the top, Just the name of the class (e.g., Dog, Student), Can be in italics if the class is abstract.

Attributes (Properties or Variables) : Shown in the middle section
and Format: visibility name: type (Example: - age: int)

```
Symbol	Visibility	      Meaning
+	      Public	      Anyone can access
-	      Private	      Only inside the class
#	      Protected	      Class & subclasses
```

Operations (Methods or Functions) : Shown in the bottom section
Format: visibility name(parameters): returnType. Example: + eat(food: String): void

Class in UML for above code 
```
-----------------------------
|          Dog              |
-----------------------------
| - name: String            |
| - breed: String           |
| - age: int                |
-----------------------------
| + bark(): void            |
| + eat(food: String): void |
-----------------------------
```

#### **Relationships Between Classes**

Relationships show how classes interact with each other.

The 6 Main Types of Class Relationships:

1. Inheritance (Generalization)

“IS-A” relationship. A subclass inherits from a superclass.Common features are defined in the parent. 

Shown with a solid line and a hollow arrowhead pointing to the parent class.
```
      Animal
        ▲
        |
       Dog
```
Dog is an Animal.

2. Association

“Uses/Has-A” relationship. A class connects to another class. Represented by a solid line between two classes. 

Can be bidirectional or unidirectional.
```
Student --------- Course
```
A Student enrolls in a Course.

3. Aggregation
“Has-A (but loosely connected)” relationship. One class contains a collection of other class objects. Parts can exist independently of the whole.

Shown by a solid line with an unfilled diamond at the “whole” side.
```
Library ◇--------- Book
```
A Library has Books, but Books can exist without the Library.

4. Composition

“Has-A (strong ownership)” relationship. Stronger version of aggregation. When the parent is destroyed, the parts are too.

Shown by a filled diamond on the “whole” side.
```
House ◆--------- Room
```
A Room cannot exist without a House.

5. Dependency
“Uses temporarily” relationship. A class uses another class as a parameter or inside a method.

Shown with a dashed arrow from user to the used class.
```
Printer <---> uses --> Ink
```
Printer depends on Ink, maybe only inside a method.

6. Realization (Interface Implementation)

“Implements an interface” relationship. One class implements an interface.

Shown by a dashed line with a hollow arrowhead.
```
     IPlayable
         ▲
         |
        Game
```
Game class implements IPlayable interface.

