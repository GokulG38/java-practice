# 02 Missing Parentheses


1. Always use parentheses when `&&` and `||` appear in the same expression to ensure correct operator precedence and readability.
2. **Logical Operators**: Think of `&&` as multiplication and `||` as addition for precedence clarity while working with boolean
3. **Simplification**: Break down complex conditions into multiple simple `if` statements or extract to separate methods
4. **Library Methods**: Leverage built-in methods like `Math.max()`, `String.repeat()`, etc. to avoid complex expressions
5. **String Formatting**: Use `String.format()` instead of concatenation when mixing strings and values
6. **Null Handling**: Apply `Objects.requireNonNullElse()` for complex null-checking conditionals

## Examples

### Instanceof with Negation
```
// Incorrect
if (!obj instanceof String) {}

// Correct
if (!(obj instanceof String)) {}
```

### Ternary in Concatenation
```
// Incorrect
return "Found " + multiple ? "multiple problems" : "a problem";

// Correct
return "Found " + (multiple ? "multiple problems" : "a problem");
```

### Math Operations
```
// Incorrect
str.length() + indent < 0 ? 0 : indent

// Correct
str.length() + Math.max(indent, 0)
```

### Null Checks with Formatting
```
// Incorrect
"Value: " + value != null ? value : "(unknown)"

// Better (extract variable)
String displayedValue = value != null ? value : "(unknown)";
return "Value: " + displayedValue;

// Best (use String.format)
return String.format("Value: %s", value != null ? value : "(unknown)");

// Alternative (use Objects utility)
return String.format("Value: %s", Objects.requireNonNullElse(value, "(unknown)"));
```