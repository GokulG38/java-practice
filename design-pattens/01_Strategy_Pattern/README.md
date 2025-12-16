# Strategy Pattern

The **Strategy Pattern** defines a family of algorithms, encapsulates each one, and makes them interchangeable.

## Design Principles

* Identify the aspects of your application that vary and separate them from what stays the same
* Build behavior by composing objects instead of relying on rigid inheritance hierarchies.
* Depend on abstractions (interfaces) rather than concrete classes to reduce coupling and increase flexibility.

## Use Case Example

Duck simulator where ducks can have different flying and quacking behaviors. By using strategies, ducks can change their behavior dynamically (Eg: a duck can start flying with wings or stop quacking)
