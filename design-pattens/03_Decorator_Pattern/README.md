# Decorator Pattern

The **Decorator Pattern** attaches additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing for extending functionality.

- 

## Design Principles

* Classes should be open for extension but closed for modification

## Use Case Example

Adding condiments like Mocha, Soy etc. to the base beverage. Each condiment is a decorator that wraps the beverage and adds its own description and cost.


## Notes

* Avoids subclass explosion - Pattern helps to avoid huge number of subclasses for every possible combination.
* Decorators have the same supertype as the objects they decorate
* The decorator adds its own behavior before and/or after delegating to the object it decorates to do the rest of the job