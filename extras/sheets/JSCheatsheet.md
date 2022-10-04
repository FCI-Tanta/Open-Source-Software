### JavaScript basics

- Variables: an abstract storage location paired with an associated symbolic name which contains some known or unknown
  value

```js
var x;
var x = 0;
var x = 'abc';
var x = true;
```

- Arithmetic Operators

| Operator         | Description                                               |
|------------------|-----------------------------------------------------------|
| + (Addition)     | Adds two operands (e.g. x + y)                            |
| - (Subtraction)  | Subtracts the second operand from the first (e.g. x - y)  |
| / (Division)     | Divides the numerator by the denominator (e.g. x / y)     |
| % (Modulus)      | Returns the remainder of an integer division (e.g. x % y) |
| ++ (Increment)   | Increases an integer value by one (e.g. x++)              |
| -- (Subtraction) | Decreases an integer value by one (e.g. x--)              |

- Comparison Operators

| Operator                       | Description                                                                                              |
|--------------------------------|----------------------------------------------------------------------------------------------------------|
| == (Equal)                     | Checks if the value of two operands are equal or not, if equals, returns true (e.g. x == y)              |
| != (Not Equal)                 | Checks if the value of two operands are equal or not, if equals, returns false (e.g. x != y)             |
| \> (Greater than)              | Checks if the value of the left operand is greater than the value in the right (e.g. x > y)              |
| \< (Less than)                 | Checks if the value of the left operand is less than the value in the right (e.g. x < y)                 |
| \>= (Greater than or Equal to) | Checks if the value of the left operand is greater than or equal to the value in the right (e.g. x >= y) |
| \<= (Less than or Equal to)    | Checks if the value of the left operand is less than or equal to the value in the right (e.g. x >= y)    |

- Logical Operators

| Operator           | Description                                              |
|--------------------|----------------------------------------------------------|
| && (Logical AND)   | Returns true if both the operands are true (e.g. x && y) |
| \|\| (Subtraction) | Subtracts the second operand from the first (e.g. x - y) |
| ! (Logical NOT)    | Returns the reverse value of the operand (e.g. !x)       |

- Assignment Operators

| Operator                    | Description                                                                                                                                                                |
|-----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| = (Simple Assignment)       | Assigns values from the right side operand to the left side operand (e.g. x = 3 + 5)                                                                                       |
| += (Add and Assigment)      | Assigns values from the current value of the left side operand *plus* the right side operand to the left side operand (e.g. x += 5, equivalent to x = x + 5)               |
| -= (Subtract and Assigment) | Assigns values from the current value of the left side operand *minus* the right side operand to the left side operand (e.g. x -= 5, equivalent to x = x - 5)              |
| *= (Multiply and Assigment) | Assigns values from the current value of the left side operand *multiple* the right side operand to the left side operand (e.g. x *= 5, equivalent to x = x * 5)           |
| /= (Divide and Assigment)   | Assigns values from the current value of the left side operand *divided by* the right side operand to the left side operand (e.g. x /= 5, equivalent to x = x / 5)         |
| %= (Modulus and Assigment)  | Assigns the *reminder* from the current value of the left side operand *divided by* the right side operand to the left side operand (e.g. x %= 5, equivalent to x = x % 5) |

### Functions

A function is a group of statements which can be called to accomplish a specific task. The function usually has the
following criterias: -
    * NAME: a special name that we give to the function to call it with.
    * Return Value (Optional): a value that the function will give back after it finishes executions.
    * Parameters (Optional): a number of values that the function takes to be able to accomplish a specific task.

```js
// Function called log with no parameters and no return value
function log() {
    console.log('Hello, World!');
}

// Function called log with one parameter and no return value
function log(name) {
    console.log('Hello, ' + name);
}

// Function called sum that takes two parameters and a return value
function sum(x, y) {
    return x + y; // Return statement that returns a value
}
```

- Prebuilt Functions: functions that already exists in JavaScript that we can use to do specific tasks.

| Function | Description                                    | Parameters                                            |
|----------|------------------------------------------------|-------------------------------------------------------|
| `prompt` | a function that asks the user to enter a value | `message`: a message to show to the user as a hint    |
| `alert`  | a function that sends a message to the user    | `message`: a message to show to the user as an output |

### Control Flow

Control Flow is the order in which the computer executes statements in a script; using a condition which is usually an
boolean expression.

- Conditional Statements: the first type of control flow statements which specify if a specific block of code will be
  executed or not.

```js
// If Statement
if (condition) {
    // running code in case condition is true
}

// If-Else Statement
if (condition) {
    // running code in case condition is true
} else {
    // running code in case condition is false
}

// If-ElseIf-Else Statement
if (condition1) {
    // running code in case condition1 is true
} else if (condition2) {
    // running code in case condition1 is false && condition2 is true
} else {
    // running code in case condition1 is false && condition2 is false
}
```

```js
// Switch Statement
switch (expression) {
    case value1:
        // running code in case expression == value1
        break;

    case value1:
        // running code in case expression == value2
        break;

    default:
    // running code in case non of the values matches the expression
}
```

- Loops: the second type of control flow statements which specify how many times a specific block of code will be
  executed.

```js
// For Loop
for (pre_statement; condition; post_statement) {
    // running code in case condition is true
}

// pre_statement: a regular js statement that will be called before the loop starts
// post_statement: a regular js statement that will be called after each iteration
```

```js
// While Loop
while (condition) {
    // running code in case condition is true
}
```

```js
// Do-While Loop
do {
    // normal running code
} while (condition); // re-execute the previous block if the condition is true
```

### Strings

Strings are a group of characters stored together denoted by single or double quotes (e.g. `var x = 'abc';`
  or `var x = "abc";`)

- Properties: -

| Property | Description                      | Syntax                    |
|----------|----------------------------------|---------------------------|
| `length` | returns the length of the string | `'abc'.length`: returns 3 |

- Member Functions (Methods): -

| Method        | Description                                                                                                                                                                                                                | Syntax                                 |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------|
| `charAt`      | returns the character at the specified index                                                                                                                                                                               | `'abc'.charAt(1)` returns 'b'          |
| `charCodeAt`  | returns a number indicating the ASCII code of the character at the specified index. Refer to [ASCII Table](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/ASCII-Table-wide.svg/1200px-ASCII-Table-wide.svg.png) | `'abc'.charCodeAt(1)` returns 98       |
| `concat`      | returns a string resulting from combining two strings                                                                                                                                                                      | `'abc'.concat('def')` returns 'abcdef' |
| `indexOf`     | returns the index of the first occurence of the specified value, or -1 if it doesn't exist                                                                                                                                 | `'abc'.indexOf('b')` returns 1         |
| `lastIndexOf` | returns the index of the last occurence of the specified value, or -1 if it doesn't exist                                                                                                                                  | `'abbc'.lastIndexOf('b')` returns 2    |
| `slice`       | returns an extracted section of the string                                                                                                                                                                                 | `'abbc'.slice(0, 2)` returns 'ab'      |
| `toLowerCase` | returns the lower case version of the string                                                                                                                                                                               | `'ABC'.toLowerCase()` returns 'abc'    |
| `toUpperCase` | returns the upper case version of the string                                                                                                                                                                               | `'abc'.toUpperCase()` returns 'ABC'    |

- Static functions: -

| Function       | Description                                          | Syntax                                |
|----------------|------------------------------------------------------|---------------------------------------|
| `fromCharCode` | returns the character from the specified ASCII value | `String.fromCharCode(97)` returns 'a' |

- Custom Operators: -

| Operator | Description                   | Syntax               |
|----------|-------------------------------|----------------------|
| +        | Converts the string to number | `+'100'` returns 100 |
