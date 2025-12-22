# 08 Confusing && and ||



1. De Morgan's law 
   1. !(a || b)  ≡  !a && !b
   2. !(a && b)  ≡  !a || !b
2. For complex conditions involving multiple operators, use intermediate variables, or extract short methods, or split the condition into several statements
3. Use advanced static analyzers capable of tracking value ranges
4. Extract repetitive conditions to temporary variables, as it helps static analysers track values
5. For unit test for methods returning boolean. Make sure to have at least one test each for true and false condition
6. Use negate if condition in IDE and remove else condition instead of doing it manually as this helps with applying De Morgan's law




```