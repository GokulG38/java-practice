# 07 Short-circuit logic operators



1. Accidental use of &, |, &= and |= etc instead of && and || can cause errors and unwanted calculations. So avoid them. Use comments "//noinspection NonShortCircuitBooleanExpression" in case usage is necessary (No compound operator available like &&=)
2. For complex conditions involving multiple operators, use intermediate variables or extract short method or split the condition into several statements

### Examples
```
//1
//Avoid
boolean checkObject(Object obj) {
    return obj instanceof First && checkFirst((First)obj) 
           | obj instanceof Second && !(obj instanceof Exclude) 
           || obj instanceof Third && checkThird((Third)obj);
}
// Use
boolean checkObject(Object obj) {
    if (obj instanceof First f) {
        return checkFirst(f);
    }

    if (obj instanceof Second && !(obj instanceof Exclude)) {
        return true;
    }

    if (obj instanceof Third t) {
        return checkThird(t);
    }

    return false;
}

//2
#For booleans, avoid
if (updateA() & updateB()) {
    …
}
#Use
boolean a = updateA();
boolean b = updateB();

if (a && b) {
    …
}



```