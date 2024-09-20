# Design Patterns

The Gang of Four (GoF) design patterns refer to 23 foundational design patterns outlined in the book "Design Patterns: Elements of Reusable Object-Oriented Software" written by four authors: Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides, who are collectively known as the "Gang of Four." These design patterns are solutions to common problems in software design, particularly in object-oriented programming.

The patterns are grouped into three categories based on their purpose:

# 1. Creational Patterns
These patterns are concerned with the creation of objects, providing ways to instantiate them while decoupling the instantiation logic from the client code.

## Abstract Factory: 
Creates families of related or dependent objects without specifying their concrete classes.
## Builder: Separates the construction of a complex object from its representation, allowing the same construction process to create different representations.
## Factory Method: Defines an interface for creating an object but allows subclasses to alter the type of object that will be created.
## Prototype: Creates new objects by copying an existing object (the prototype).
## Singleton: Ensures a class has only one instance and provides a global point of access to it.
# 2. Structural Patterns
These patterns deal with the composition of classes or objects, forming larger structures while maintaining flexibility and efficiency.

## Adapter: Converts the interface of a class into another interface the client expects.
## Bridge: Decouples an abstraction from its implementation, allowing them to vary independently.
## Composite: Composes objects into tree-like structures to represent part-whole hierarchies. Clients treat individual objects and compositions uniformly.
## Decorator: Adds additional responsibilities to an object dynamically.
## Facade: Provides a unified interface to a set of interfaces in a subsystem, making it easier to use.
## Flyweight: Uses sharing to support large numbers of fine-grained objects efficiently.
## Proxy: Provides a surrogate or placeholder for another object to control access to it.
# 3. Behavioral Patterns
These patterns focus on communication between objects, defining how they interact and distribute responsibilities.

# Chain of Responsibility: Passes a request along a chain of handlers, allowing the processing to happen at various points in the chain.
# Command: Encapsulates a request as an object, allowing for parameterization and queuing of requests.
# Interpreter: Implements a grammar and interpreter for a language.
# Iterator: Provides a way to access elements of a collection sequentially without exposing its underlying representation.
# Mediator: Defines an object that encapsulates how a set of objects interact, promoting loose coupling.
# Memento: Captures and externalizes an object’s internal state without violating encapsulation, so the object can be restored later.
# Observer: Establishes a one-to-many dependency between objects, so when one object changes state, all its dependents are notified.
# State: Allows an object to alter its behavior when its internal state changes, appearing as though it changes class.
# Strategy: Defines a family of algorithms, encapsulates each one, and makes them interchangeable.
# Template Method: Defines the skeleton of an algorithm in a method, deferring some steps to subclasses.
# Visitor: Represents an operation to be performed on elements of an object structure, allowing new operations without modifying the elements.
## Why These Patterns Matter
The Gang of Four patterns offer time-tested solutions to recurring design problems. They promote best practices like loose coupling, encapsulation, and modularity, making systems more maintainable and scalable. These patterns are foundational in object-oriented design and are widely adopted across many programming languages, including Java, C++, and Python.






