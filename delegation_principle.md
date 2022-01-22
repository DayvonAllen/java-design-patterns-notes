## Delegation Principle
- the concept of one class `delegating` its behavior to another class
  - don't do all stuff by yourself, delegate it to a respective class
- can be viewed as a relationship between objects where one objects forwards certain method calls to another object, called its `delegate`
- delegation is an extreme example of object composition.
  - shows that you can always replace inheritance with object composition as mechanism for code reuse
  - delegation means that you use an object of another class as an instance variable, and forward messages to the instance.
---