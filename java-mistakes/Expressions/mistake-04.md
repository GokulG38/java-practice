# 04 Multiline string literals


1. String concatenation has lower precedence than method calls. Therefore, wrap method call qualifier in parentheses
2. Use text blocks instead of complex string concatenations and use replace() to add variable. Example: .replace("$user$", userName)
