# 03 Accidental concatenation


1. Numbers are implicitly converted to String while used in concatenation
2. Avoid using arithmetic operations and string concatenations in single expression

## Examples

### Instanceof with Negation
```
// Incorrect
"String entryName = "Entry#" + index + 1;"

// Correct
"String entryName = "Entry#" + (index + 1);"

// Better
"int adjustedIndex = index + 1;
String entryName = "Entry#" + adjustedIndex;"

// Robust
"String entryName = String.format("Entry#%d", index + 1);"
```

