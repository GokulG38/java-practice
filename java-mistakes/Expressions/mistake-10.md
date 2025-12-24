# 10 Conditional operators and variable arity calls


1. In conditional operator, if the type of first branch is string and the second is Object[], 
the result is considered as their super type Object and wraps it to Array.
2. We can avoid this by using manual Object[] wrapper for the first branch, or use If else statement instead.
3. Notice IDEA warning - Suspicious Ternary Operator in Varargs Method Call inspection

### Examples
```

//Avoid

System.out.printf(formatString, params.length == 0 ? "user" : params);

Params will be printed as "[Ljava.lang.Object;...."

//Use

System.out.printf(formatString, params.length == 0 ? new Object[]{"user"} : params);

OR
 
if (params.length == 0) {
    System.out.printf(formatString, "user");
} else {
    System.out.printf(formatString, params);
}


```