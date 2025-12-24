# 09 Incorrect usage of variable arity



1. When you use var args, java treats it as array internally. 
2. When passing an array to a varargs method, the argument must be declared as Object[] (or varargs element type) for
it to be treated as the varargs array. If it's declared as Object, it will be treated as a single element. See Example 2
3. Similarly, If null is passed to a varargs method and the argument is declared as an array of the varargs element
type (eg: Object[]), the varargs array itself will be null, which can cause a NullPointerException when iterated. 
If null is passed as a single element (declared as Object), it becomes an element inside the varargs array, not the array itself.
4. Avoid using Collection instead of Array in varargs method call. Collection wll be treated as single element
5. Do not use Array.asList() with primitive values, as the array will be treated as single element. Stream and box the values to wrapper types before working with Array.asList.
6. Use IDE's "Confusing Argument to Varargs Method" inspection and Sonarlint's S5669 tool to hto catch these issues early.


### Examples
```
//1
//Normal Var args method

static void printAll(Object... data) {
   for (Object d : data) {
        System.out.println(d);
    }
}

We can call the above method by 
-printAll("Hello", "World");
-printAll(new Object[] {"Hello", "World"});


//2
static void printAll(Object... data) {
   for (Object d : data) {
        System.out.println(d);
    }
}


Object obj = new Object[]{"Hello", "World"};
printAll(obj);
-Calling method like this won't provide desired output. Output will look something like [Ljava.lang.Object;@7106e68e


Object obj[] = new Object[]{"Hello", "World"};
-This will print the strings




```