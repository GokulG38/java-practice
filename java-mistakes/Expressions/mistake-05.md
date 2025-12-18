# 05 Unary plus



1. Typos like =+ instead of +=, which possibly won't throw an error, but mathematical operation done is different
2. Applying unary + with character leads to conversion to code
3. Arithmetic operations applied to character literals can cause compilation error. So avoid using character literals in favour of string literals. Use "\"" instead of '"'
4. Avoid unary + completely as it do not have any practical value and configure static analysers to report them. This helps us find bugs.

### Example
```
// Incorrect
return "User not found: " +
       + '"' + user + '"';

// Correct
"User not found: " + "\"" + user + "\""
```