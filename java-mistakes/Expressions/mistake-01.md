# 01 Java Operator Precedence

>  Using numerical operators without knowing their priority can cause logic errors.  
>  Use explicit parentheses to avoid mistakes (do not blindly rely on static analysers).  
>  Avoid using bitwise shift instead of multiplication or division — JIT and AOT compilers already optimize them to equivalent machine code, so performance is the same.  
>  Use `Object.hashCode()` instead of writing manual hash functions.

## 1. Postfix
`a++`, `a--`

## 2. Prefix / Unary
`++a`, `--a`, `+a`, `-a`, `~`, `!`

## 3. Multiplicative
`*`, `/`, `%`

## 4. Additive
`+`, `-`

## 5. Shift
`<<`, `>>`, `>>>`

## 6. Relational
`<`, `>`, `<=`, `>=`, `instanceof`

## 7. Equality
`==`, `!=`

## 8. Bitwise AND
`&` — Both bits must be **1** for the result to be **1**.

## 9. Bitwise XOR
`^` — The result is **1** if the bits are **different** (one true, one false).

## 10. Bitwise OR
`|` — The result is **1** if **any** bit is 1.

## 11. Logical AND
`&&`

## 12. Logical OR
`||`

## 13. Conditional (Ternary)
`? :`

## 14. Assignment
`=`, `+=`, `-=`, `*=`, `/=`, `%=`, `&=`, `^=`, `|=`, `<<=`, `>>=`, `>>>=`

--------------------------------------------------------------------------

# Useful Bitwise Equations

- `~x = -(x + 1)`
- `x << n == x × 2ⁿ`
- `x >> n == x / 2ⁿ`
- `a >>> n = floor( (a mod 2³²) / 2ⁿ )`

