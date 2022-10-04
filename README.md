# ST211: Open Source Software

<p align="justify">
The practical objective of this course you will learn how to participate in OSS projects
by improving aspects of the software that they feel that they're wrong, suggesting
possible improvement, or just raising issues for the existing solutions.
As a side object of this course you will learn C# which an open source language created by
Microsoft in 2000 and originally started as closed source project and then converted to
an open source project in 2015 as a part of Microsoft's software revolution.
</p>

## Section 0: Recap

### Section Objectives

Part 1 -
- Recap on HTML boilerplate and basics
- Recap on JS syntax and basic programming skills
- Recap on String manipulation

Part 2 -
- Recap on Arrays
- Recap on some Algorithms
- Recap on some Data Structures
- Recap on OOP

### HTML boilerplate

A simple HTML document should start by something like that: -

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Page Title</title>
</head>

<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

<script src="script.js"></script>

</body>

</html>
```

- The `<!DOCTYPE html>` declaration defines that this document is an HTML5 document
- The `<html>` element is the root element of an HTML page
- The `<head>` element contains metadata about the HTML page, such as title, name, description, ...
- The `<title>` element specifies a title for the HTML page (which is shown in the browser's title bar or in the page's
  tab)
- The `<body>` element defines the document's body, and is a container for all the visible contents, such as headings,
  paragraphs, images, hyperlinks, tables, lists, etc.
- The `<h1>` element defines a large heading
- The `<p>` element defines a paragraph
- The `<script>` element specifies some JavaScript code that must be implemented once the element is rendered

### HTML basics

- HTML elements:

```html 
<tagname></tagname>
<tagname>[content]</tagname>
<tagname attribute="value">[content]</tagname>
<tagname attribute1="value" attribute2="value2">[content]</tagname>
```

- HTML self-closing elements:

```html 
<tagname />
```

- [HTML Tags](./htmlcheatsheet.pdf)

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

### Task 1: HTML boilerplate

```
Create a web page that meets the following criterias: -
1) Has your NAME as the title
2) Has the COURSE_NAME in a large heading
3) Has your NAME in a paragraph
4) Renders a 'script.js' file 
```

### Task 2: Greeting with the user's name

```
Create a web page that do the following: -
1) Asks the user for this name in a dialog
2) Outputs a welcome message with this name in another dialog

Example:
IN> Ibrahim
OUT> Welcome, Ibrahim!
```

### Task 3: Square of a number

```
Create a web page that do the following: -
1) Asks the user for a number in a dialog
2) Outputs the square of that number in another dialog

Example:
IN> 2
OUT> 4
```

### Task 4: Average of two integers

```
Create a web page that do the following: -
1) Asks the user for two numbers in a dialog
2) Outputs the average of these two numbers in another dialog

Example:
IN> 2
IN> 4
OUT> 3
```

### Task 5: Adding N integers

```
Create a web page that do the following: -
1) Asks the user for a number (N) in a dialog
2) Asks the user for others numbers N times in a dialog
3) Outputs the N numbers in another dialog

Example:
IN> 3
IN> 1
IN> 2
IN> 3
OUT> 6
```

### Task 6: Converting Celsius to Fahrenheit

```
Create a web page that do the following: -
1) Asks the user for a number (C) in a dialog
2) Outputs the corresponding value of this number in fahrenheit in another dialog

Example:
IN> 40
OUT> 104
```

### Task 7: Converting String to Uppercase (2 methods)

```
Create a web page that do the following: -
1) Asks the user for a string in a dialog
2) Outputs the upper case of this string in another dialog

Example:
IN> ibrahim
OUT> IBRAHIM
```

### Task 8: Adding string ranks

```
Create a web page that do the following: -
1) Asks the user for a string in a dialog
2) Outputs the sum of the string characters' ranks in the alphabtical order in another dialog

Example:
IN> abc
OUT> 6

Explanation:
a = 1, b = 2, c = 3

```