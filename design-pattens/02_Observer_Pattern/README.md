# Observer Pattern

The **Observer Pattern** defines a one to many dependency between objects so that when one object changes state, all of its dependents are notified and updated automatically.

- Simply, Publisher + Observer => Observer Pattern
- Observer object register with Subject to get updates

## Design Principles

* Strive for loosely coupled designs between objects that interact

## Use Case Example

Weather station updates multiple displays whenever the weather data object changes

## Notes

* Loose coupling minimise interdependency and create flexible OO design
* We don't have to modify Subject to add new observer and only thing Subject knows about observer is that it implements Observer Interface
