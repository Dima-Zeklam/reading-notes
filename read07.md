# JavaScript 

## JavaScript Expressions and operators

###  1. Assignment operators
#### An assignment operator assigns a value to its left operand based on the value of its right operand. The simple assignment operator is equal `(=)`, which assigns the value of its right operand to its left operand. That is, `x = y` assigns the value of `y` to `x`.

- **Compound assignment operators**

Name                    |	Shorthand operator   |  Meaning
------------------------|----------------------|-----------
Assignment              |	x = y	               | x = y
Addition assignment	    |x += y                |	x = x + y
Subtraction assignment  |	x -= y               |x = x - y
Multiplication assignment|	x *= y             |	x = x * y
Division assignment	    | x /= y               |x = x / y
Remainder assignment    |	x %= y               |	x = x % y
Exponentiation assignment|	x \**= y         	| x = x \** y
Logical AND assignment|x &&= y	|x && (x = y)
Logical OR assignment|	x \|\|= y	x | \|\| (x = y)
Logical nullish assignment	|x ??= y          |	x ?? (x = y)

- Destructuring
>var foo = ['one', 'two', 'three'];

 >// without destructuring

 >var one   = foo[0];

  >var two   = foo[1];

 >var three = foo[2];

  >// with destructuring

  >var [one, two, three] = foo;


- JavaScript Bitwise Operators

Name                    |	Shorthand operator   |  Meaning
------------------------|----------------------|-----------
Left shift assignment   | x <<= y	           | x = x << y 
Right shift assignment| 	x >>= y              |	x = x >> y
Unsigned right shift assignment|	x >>>= y	|x = x >>> y
Bitwise AND assignment|	x &= y               	|x = x & y
Bitwise XOR assignment|	x ^= y	               | x = x ^ y
Bitwise OR assignment	|x = y	| x = x \| y

### 2. Comparison operators
#### A comparison operator compares its operands and returns a logical value based on whether the comparison is true.


  Operator       | 	Description    |  Comparing| return
-----------------|-----------------|-----------|--------
== |	equal to	| x == 8 |	false	
| | | x == 5	|true	
| | | x == "5"	|true	
===	| equal value and equal type|	x === 5	|true	
| | |x === "5"|	false	
!=	|not equal	|x != 8	|true	
!==	 |not equal value or not equal type|	x !== 5|	false	
|||x !== "5"|	true	
| | | x !== 8 |	true	
\> |	greater than|	x > 8|	false	
\< |	less than|	x < 8	|true	
\>= |	greater than or equal to|	x >= 8	|false	
<= |	less than or equal to|x <= 8|	true
