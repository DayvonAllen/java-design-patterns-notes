# Design Smells
- `Design Smells` - structures in the design that indicate violations of fundamental design principles and negatively impact design quality.
- `Java Code Smells`:
  - If several classes duplicate the same 90% of code, we should use inheritance to remove the duplication.
  - Too many public classes, members, and methods
    - violates encapsulation
  - Classes that are too large(violates cohesion or is doing too many things)
    - combining every single concept in your app into one massive class
- Design smells often end up creating code that is:
  - hard to read
  - breaks easily
  - hard to maintain(adding new features or doing basic bug fixing)
- Always strive for highly cohesive(has a single purpose) and loosely coupled(isn't heavily dependent on the implementation of another object)solutions, code and design. 
- Should always program to an interface(a supertype), allow abstraction and leads to more flexible code.
  - common theme of design patterns
  - helps provide `loose coupling` because it greatly reduces implementation dependencies between subsystems.
  - allows us to exploit polymorphism(runtime or dynamic type checking), based on the instance type, not the reference type
---
  
## Java Composition and Aggregation
- `composition` - an object contains(owns) another object as a member variable of its class.
- composition allows for code reuse from final classes(however you can't use inheritance with final classes)
- composition is a `has-a` relationship, inheritance is an `is-a` relationship.
  - composition helps keep each class encapsulated and focused on one task, which is why it should be favored over inheritance
  - inheritance breaks encapsulation because `sub-classes` are dependent upon the base class behavior
    - inheritance is tightly coupled whereas composition is loosely coupled.
    - when behavior of the `super class` changes, functionality in a `sub-class` may be broken, without any change on its part. 
- `aggregation` - implies a relationship where the child can exist independently of the parent(also a `has-a` relationship):
  - a collection of things that are not part of it
  - airplanes at an airport
  - students in a class - get rid of the class and the students still exist
  - tires on a car - the tires can be taken off of the car and installed on a different one.
- `aggregation` and `composition` are almost completely the same except that composition is used when the life of the child is completely controlled by the parent
  - the distinction loses much of its importance in languages that have garbage collections
    - you do not have to concern yourself with the life of the object.
---
  
## Abstract Classes vs Interfaces In Java
- variables in interfaces are `public static final`
- abstract classes can have other access modifiers for variables(`private, protected, etc.`)
- methods in interfaces are `public or public static`
- methods in abstract classes can be `private and protected too`
- When to use `Abstract classes`:
  - `utilize abstract classes to establish a relationship between interrelated objects`
    - `when you want to share code among several closely related classes then this common state or behavior can be put in the abstract class`
- When to use `Interfaces`:
  - utilize interfaces to establish a relationship between unrelated classes
    - the interfaces `Comparable` and `Cloneable` are implemented by many unrelated classes.
  - utilize interfaces if you want to specify the behavior of a particular data type, but are not concerned about who implements its behavior.
  - utilize interfaces to take advantage of multiple inheritance
---

# General Design Smells

## Rigidity
- the tendency of software to be difficult to change.
- a single change causes a cascade of subsequent changes in dependent modules(tight coupling)
- the more modules that must be changed, the more rigid the design.
---

## Fragility
- the tendency of software to break in many places when a single change is made
- the problems often occur in places that have no obvious relation to the area that was changed
- as the fragility of a module increases, the likelihood that a change will introduce unexpected programs rise.
---

## Rigidity vs Fragility
- Rigidity comes from one change while fragility tends to come from multiple changes
---

## Immobility
- contains parts that could be useful in other systems, but the effort and risk of separating them from the original system are too great,
---

## Viscosity
- A system has a high viscosity if a design-preserving change is more difficult to use than a hack(or a shortcut)
- If running unit tests and compilation takes a lot of time, it is likely for a developer to bypass procedures and implement a hack without running all automated tests
---

## Needless Repetition
- copy and pasting code throughout the system
- happens when necessary abstractions have not been made
---

## Opacity
- the tendency of a module to be difficult to understand
- when code is not written in a clear and expressive manner, it is said to be `opaque`
- code that evolves over time tends to become more difficult to understand over time.
---

## Needless Complexity
- one of the most important smells of bad design
- in a passionate attempt to avoid the other smells, developers introduce all sorts of abstractions and preparations for potential changes in the future
  - good software design is lightweight, flexible, easy to read and understand and above all easy to change
  - there is no need to keep into account all potential changes in the future
  - do not `over-design`
---