# Strategy Pattern Example

## Core components

* **Strategy Interface**: Defines the contract for all algorithms (flying, quacking).
* **Concrete Strategy Classes**: Implement the strategy interface for specific behaviors (`FlyWithWings`, `Quack`).
* **Context Class**: Holds a reference to a strategy and uses it to perform actions.

---

## Strategy Interfaces

```java
public interface FlyBehavior {
    void fly();
}

public interface QuackBehavior {
    void quack();
}
```

---

## Concrete Strategy Implementations

```java
public class FlyWithWings implements FlyBehavior {
    public void fly() {
        System.out.println("I'm flying with wings!");
    }
}
```

```java
public class Quack implements QuackBehavior {
    public void quack() {
        System.out.println("Quack");
    }
}
```

---

## Context Class

```java
public class Duck {
    private FlyBehavior flyBehavior;
    private QuackBehavior quackBehavior;

    public Duck(FlyBehavior flyBehavior, QuackBehavior quackBehavior) {
        this.flyBehavior = flyBehavior;
        this.quackBehavior = quackBehavior;
    }

    public void performFly() {
        flyBehavior.fly();
    }

    public void performQuack() {
        quackBehavior.quack();
    }

    public void setFlyBehavior(FlyBehavior flyBehavior) {
        this.flyBehavior = flyBehavior;
    }
}
```

---

## Test Class

```java
public class DuckTest {
    public static void main(String[] args) {
        Duck mallard = new Duck(new FlyWithWings(), new Quack());
        mallard.performFly();
        mallard.performQuack();
    }
}
```

---




