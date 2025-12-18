# 06 Implicit type conversion in conditional expression



1. Avoid boxed primitives as implicit unboxing may lead to null pointer error. When used in generic expressions, make sure to convert them early to primitives.
2. Use if statements over conditional statements. if statements do conversion at each return, while the conditional operator must first force both branches into a single common type ie, implicit unboxing.
3. For standalone expressions, surrounding context do not affect its type.
4. Nested conditional expressions too has similar issues. Implicit unboxing can lead to NullPointerException. So it is better to choose if statement.
5. Avoid conditional expressions that return different types after ? and :.

### Example of implicit conversion
```
// Method
Double valueOrZero(boolean condition, Double value) {
    return condition ? value : 0.0;
}


// Implicity conversion
return Double.valueOf(
    condition ? value.doubleValue() : 0.0
);

Here, if the condition is true and value is null, it throws null pointer exception
Rule behind- If one side is boxed and the other is primitive, the primitive type wins
```