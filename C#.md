# ST211: Open Source Software

<p align="justify">
The practical objective of this course you will learn how to participate in OSS projects
by improving aspects of the software that they feel that they're wrong, suggesting
possible improvement, or just raising issues for the existing solutions.
As a side object of this course you will learn C# which an open source language created by
Microsoft in 2000 and originally started as closed source project and then converted to
an open source project in 2015 as a part of Microsoft's software revolution.
</p>

## Introduction to C# and .NET Core

.NET is a free and open-source, managed computer software framework for Windows, Linux, and macOS operating systems. It
is a cross-platform successor to .NET Framework. The project is primarily developed by Microsoft employees by way of the
.NET Foundation, and released under the MIT License.

.NET Core is one of the most popular frameworks. It is used for building different types of applications using .NET
runtime. In 2016, a new version of .NET framework is introduced which is open-source and cross platform. This updated
framework is known as .NET Core and it can be run on Windows, Linux, and macOS.

.NET Core is faster web-development framework than the other available frameworks. It is designed to allow runtime
components, APIs, compilers and languages evolve quickly while still providing a stable and supported platform to keep
apps running. According to Stackoverflow developer survey 2020, it is one of the most popular and most loved frameworks.

## DotNet SDK

DotNet SDK is a set of libraries and tools that allow developers to create .NET applications and libraries.
It also contains the `dotnet cli` that can be used to build and run .NET applications.

Some of the `dotnet cli` commands that we're going to use are the following: -

| Command        | Description                                                                             | Usage                   | Example              |
|----------------|-----------------------------------------------------------------------------------------|-------------------------|----------------------|
| `dotnet new`   | Creates a new project, configuration file, or solution based on the specified template. | `dotnet new <TEMPLATE>` | `dotnet new console` |
| `dotnet build` | Builds a project and all of its dependencies.                                           | `dotnet build`          | `dotnet build`       |
| `dotnet run`   | Runs source code without any explicit compile or launch commands.                       | `dotnet run`            | `dotnet run`         |

## C# Projects (csproj file)

The `*.csproj` file is just an XML (HTML alike) file that is used by the DotNet SDK to understand the key components and
properties of the C# project.

To make any C# project, you start by creating a `*.csproj` file (e.g. `HelloWorld.csproj`) that looks like the
following: -

```xml
<!-- 'Project' is a tag that indicate the start of a project -->
<!-- 'Sdk' is a property that indicate which SDK are using, in this case, we're using Microsoft DotNet SDK -->
<Project Sdk="Microsoft.Net.Sdk">

    <!-- 'PropertyGroup' is tag that can be used to group a collection of properties  -->
    <PropertyGroup>
        <!-- 'TargetFramework' is a required tag that indicates the name of the framework that you're using -->
        <TargetFramework>net6.0</TargetFramework>

        <!-- 'OutputType' is a required tag that indicates the expected output type of the project -->
        <!-- Values can be one of the following (Library, Exe, Module, Winexe) -->
        <OutputType>Exe</OutputType>

        <!-- 'LangVersion' is an optional tag that indicates the language version that you're using -->
        <!-- Values can be one of the following (latest, preview, 10.0, 9.0, ...) -->
        <LangVersion>latest</LangVersion>
    </PropertyGroup>

</Project>
```

## C# Syntax

To make a C# program that prints a "Hello, World", you can start by make a file (e.g. Program.cs) and then write the
following: -

```csharp
// 'using' is a directive that includes a predefined library
// 'System' is a predefined namespace (C# library) which is just a collection of C# types that we can use in our program.
using System;

// 'namespace' is a keyword used to define a new namespace
// 'HelloWorld' is just the namespace of that class
namespace HelloWorld;

// A class is extensible template for creating objects that represent wide range of functionalities.
// 'public' is an access modifier that can make the preceding type accessible in all over the assembly.
// 'class' is keyword used to define a new C# class
// 'Hello' is just the name of that class
public class Hello
{
    // A method is just a block of code (statements) which can be run by calling it.
    // 'private' is an access modifier that can make the preceding type accessiable only withing the parent type.
    // 'static' is a keyword used to highlight a method so that it can be used without the need for a class instance.
    // 'void' is a keyword used to indicate that the preceding method doesn't have a return type.
    // 'Main' is just the name of that method, and it's also understood by the dotnet sdk that it's the starting point of the application.
    private static void Main()
    {
        // A static class is a class that contain only static members and you can't make an instance of that class.
        // 'Console' is a static class that can be used to manipulate the console screen.
        // 'WriteLine' is a static method that can be used to write a string to the console and ending it with a new line.
        Console.WriteLine("Hello, World");
    }
}
```

## Intrinsic Types

Intrinsic types are types predefined and always accessible. The two classes of intrinsic types are
numeric and non-numeric, with a number of types comprising each class.

### Integral Types

The *integral numeric types* represent integer numbers. All integral numeric types are value types. They're also simple
types and can be initialized with literals. All integral numeric types support arithmetic, bitwise logical, comparison,
and equality operators.

| C# type/keyword | Range                                                   | Size                              | .NET type       |
|-----------------|---------------------------------------------------------|-----------------------------------|-----------------|
| `sbyte`         | -128 to 127                                             | Signed 8-bit integer              | System.SByte    |
| `byte`          | 0 to 255                                                | Unsigned 8-bit integer            | System.Byte     |
| `short`         | -32,768 to 32,767                                       | Signed 16-bit integer             | System.Int16    |
| `ushort`        | 0 to 65,535                                             | Unsigned 16-bit integer           | System.UInt16   |
| `int`           | -2,147,483,648 to 2,147,483,647                         | Signed 32-bit integer             | System.Int32    |
| `uint`          | 0 to 4,294,967,295                                      | Unsigned 32-bit integer           | System.UInt32   |
| `long`          | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 | Signed 64-bit integer             | System.Int64    |
| `ulong`         | 0 to 18,446,744,073,709,551,615                         | Unsigned 64-bit integer           | System.UInt64   |
| `nint`          | Depends on platform (computed at runtime)               | Signed 32-bit or 64-bit integer   | System.IntPtr   |
| `nuint`         | Depends on platform (computed at runtime)               | Unsigned 32-bit or 64-bit integer | System.UIntPtr  |

In all of the table rows except the last two, each C# type keyword from the leftmost column is an alias for the
corresponding .NET type. The keyword and .NET type name are interchangeable. For example, the following declarations
declare variables of the same type: -

```csharp
int a = 123;
System.Int32 b = 123;
```

Each of the integral types has `MinValue` and `MaxValue` properties that provide the minimum and maximum value of that
type.

Integer literals can be one of the following: -

- *decimal*: without any prefix
- *hexadecimal*: with the `0x` or `0X` prefix
- *binary*: with the `0b` or `0B` prefix

The following code demonstrates an example of each: -

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

NOTE: The preceding example also shows the use of `_` as a *digit separator*. You can use the digit separator with all
kinds
of numeric literals.

NOTE: The default type for the integer literals is `int`.

If the determined type of an integer literal is `int` and the value represented by the literal is within the range of
the destination type, the value can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`
, `nint` or `nuint`:

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

As the preceding example shows, if the literal's value isn't within the range of the destination type, a compiler
error `CS0031` occurs.

You can also use a cast to convert the value represented by an integer literal to the type other than the determined
type of the literal: -

```csharp
var signedByte = (sbyte) 42;
var longVariable = (long) 42;
var longVariable2 = 42L;
```

### Floating-point Types

The *floating-point numeric types* represent real numbers. All floating-point numeric types are value types. They are
also simple types and can be initialized with literals. All floating-point numeric types support arithmetic, comparison,
and equality operators.

C# supports the following predefined floating-point types:

| C# type/keyword  | Approximate range                                    | Precision     | Size     | .NET type      |
|------------------|------------------------------------------------------|---------------|----------|----------------|
| `float`          | ±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup>    | ~6-9 digits   | 4 bytes  | System.Single  |
| `double`         | ±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup>  | ~15-17 digits | 8 bytes  | System.Double  |
| `decimal`        | ±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup> | 28-29 digits  | 16 bytes | System.Decimal |

In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type. They
are interchangeable. For example, the following declarations declare variables of the same type:

```csharp
double a = 12.3;
System.Double b = 12.3;
```

The default value of each floating-point type is zero, `0`. Each of the floating-point types has the `MinValue`
and `MaxValue` constants that provide the minimum and maximum finite value of that type. The `float` and `double` types
also provide constants that represent not-a-number and infinity values. For example, the `double` type provides the
following constants: `double.NaN`, `double.NegativeInfinity`, and `double.PositiveInfinity`.

The type of a real literal is determined by its suffix as follows: -

- The literal **without suffix** or with the `d` or `D` suffix is of type `double`
- The literal with the `f` or `F` suffix is of type `float`
- The literal with the `m` or `M` suffix is of type `decimal`

The following code demonstrates an example of each:

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;
float f = 3_000.5F;
f = 5.4f;
decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

### Type Conversion

We use `System.Convert` class static methods to convert from type to type and mainly from string to any numeric type.

```csharp
int i = Convert.ToInt32("12");
double d = Convert.ToDouble("12.5");
```

Or, more easily we can use the built-in methods in every type as following: -

```csharp
int i = int.Parse("12");
double d = double.Parse("12.5");
```

## Operators

C# provides a number of operators. Many of them are supported by the built-in types and allow you to perform basic
operations with values of those types. Those operators include the following groups: -

- *Arithmetic operators* that perform arithmetic operations with numeric operands
- *Comparison operators* that compare numeric operands
- *Boolean logical operators* that perform logical operations with bool operands
- *Bitwise and shift operators* that perform bitwise or shift operations with operands of the integral types
- *Equality operators* that check if their operands are equal or not

The following operators perform *arithmetic operations* with operands of numeric types: -

- Unary ++ (increment), -- (decrement), + (plus), and - (minus) operators
- Binary * (multiplication), / (division), % (remainder), + (addition), and - (subtraction) operators

The following operators perform *comparison operations* with operands of numeric types: -

The < (less than), > (greater than), <= (less than or equal), and >= (greater than or equal) comparison, also known as
relational, operators compare their operands. Those operators are supported by all integral and floating-point numeric
types.

The following operators perform *logical operations* with bool operands: -

- Unary ! (logical negation) operator.
- Binary & (logical AND), | (logical OR), and ^ (logical exclusive OR) operators. Those operators always evaluate both
  operands.
- Binary && (conditional logical AND) and || (conditional logical OR) operators. Those operators evaluate the right-hand
  operand only if it's necessary.

The following operators perform *bitwise or shift operations* with operands of the integral numeric types or the char
type: -

- Unary ~ (bitwise complement) operator
- Binary << (left shift), >> (right shift), and >>> (unsigned right shift) operators
- Binary & (logical AND), | (logical OR), and ^ (logical exclusive OR) operators

The == (equality) and != (inequality) operators check if their operands are equal or not.

## Statements

The following table lists the various types of statements in C# and their associated keywords, with links to topics that
include more information: -

| Category               | C# keywords / notes                                                                                                                                                                                                                                                          |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Declaration statements | A declaration statement introduces a new variable or constant. A variable declaration can optionally assign a value to the variable. In a constant declaration, the assignment is required.                                                                                  |
| Expression statements  | Expression statements that calculate a value must store the value in a variable.                                                                                                                                                                                             |
| Selection statements   | Selection statements enable you to branch to different sections of code, depending on one or more specified conditions. For more information, see the following topics: <ul><li>if</li><li>switch</li></ul>                                                                  |
| Iteration statements   | Iteration statements enable you to loop through collections like arrays, or perform the same set of statements repeatedly until a specified condition is met. For more information, see the following topics: <ul><li>do</li><li>for</li><li>foreach</li><li>while</li></ul> |
| Jump statements        | Jump statements transfer control to another section of code. For more information, see the following topics: <ul><li>break</li><li>continue</li><li>return</li></ul>                                                                                                         |

### Declaration Statements

```csharp
// Variable declaration statements.
var area = 2D;
double area; // no initalized vlaue
double radius = 2;

// Constant declaration statement.
const double pi = 3.14159;
```

### Expression Statements

```csharp
// Expression statement (assignment).
area = 3.14 * (radius * radius);

// Error. Not  statement because no assignment:
//circ * 2;

// Expression statement (method invocation).
System.Console.WriteLine();
```

### Selection Statements

```csharp
DisplayWeatherReport(15.0);  // Output: Cold.
DisplayWeatherReport(24.0);  // Output: Perfect!

void DisplayWeatherReport(double tempInCelsius)
{
    if (tempInCelsius < 20.0)
    {
        Console.WriteLine("Cold.");
    }
    // Optional depending on the logic
    else if (tempInCelsius >= 40.0)
    {
        Console.WriteLine("Hot.");
    }
    // Optional depending on the logic
    else
    {
        Console.WriteLine("Perfect!");
    }
}
```

```csharp
DisplayMeasurement(-4);  // Output: Measured value is -4; too low.
DisplayMeasurement(5);  // Output: Measured value is 5.
DisplayMeasurement(30);  // Output: Measured value is 30; too high.
DisplayMeasurement(double.NaN);  // Output: Failed measurement.

void DisplayMeasurement(double measurement)
{
    switch (measurement)
    {
        case < 0.0:
            Console.WriteLine($"Measured value is {measurement}; too low.");
            break;

        case > 15.0:
            Console.WriteLine($"Measured value is {measurement}; too high.");
            break;

        case double.NaN:
            Console.WriteLine("Failed measurement.");
            break;

        default:
            Console.WriteLine($"Measured value is {measurement}.");
            break;
    }
}
```

### Iteration Statements

```csharp
for (int i = 0; i < 5; i++)
{
    Console.Write(i);
}
// Output:
// 01234
```

```csharp
int n = 0;
while (n < 5)
{
    Console.Write(n);
    n++;
}
// Output:
// 01234
```

```csharp
int n = 0;
do
{
    Console.Write(n);
    n++;
} while (n < 5);
// Output:
// 01234
```

## Arrays

You can store multiple variables of the same type in an array data structure. You declare an array by specifying the
type of its elements.

### Types & Creation

```csharp
public class TestArraysClass
{
    private static void Main()
    {
        // Declare a single-dimensional array of 5 integers.
        var array1 = new int[5];

        // Declare and set array element values.
        var array2 = new int[] { 1, 3, 5, 7, 9 };

        // Alternative syntax.
        int[] array3 = { 1, 2, 3, 4, 5, 6 };

        // Declare a two dimensional array.
        var multiDimensionalArray1 = new int[2, 3];

        // Declare and set array element values.
        int[,] multiDimensionalArray2 = { { 1, 2, 3 }, { 4, 5, 6 } };

        // Declare a jagged array.
        var jaggedArray = new int[6][];

        // Set the values of the first array in the jagged array structure.
        jaggedArray[0] = new int[4] { 1, 2, 3, 4 };
    }
}
```

### Properties & Operations

An array has the following properties: -

- An array can be single-dimensional, multidimensional or jagged.
- The number of dimensions and the length of each dimension are established when the array instance is created. These
  values can't be changed during the lifetime of the instance.
- The default values of numeric array elements are set to zero, and reference elements are set to null.
- A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to null.
- Arrays are zero indexed: an array with n elements is indexed from 0 to n-1.
- Array elements can be of any type, including an array type.
- For value types, the array elements are initialized with the default value, the 0-bit pattern; the elements will have
  the value 0.
- All the reference types (including the non-nullable), have the values null.

```csharp
public class TestArraysClass
{
    private static void Main()
    {
        // Declare and initialize an array.
        var theArray = new int[5, 10];
        
        theArray[0, 0] = 1;
        
        System.Console.WriteLine("The array has {0} dimensions.", theArray.Rank);
        System.Console.WriteLine("The array has {0} at the beginning.", theArray[0, 0]);
    }
}
// Output:
// The array has 2 dimensions.
// The array has 1 at the begining.
```

## Char & Strings

### Char type & operations

Char type in C# represents a character as a UTF-16 code unit.

```csharp
public class CharStructureSample
{
    private static void Main()
    {
        var chA = 'A';
        char ch1 = '1';
        string str = "test string";

        Console.WriteLine(chA.CompareTo('B'));          // Output: "-1" (meaning 'A' is 1 less than 'B')
        Console.WriteLine(chA.Equals('A'));             // Output: "True"
        Console.WriteLine(char.GetNumericValue(ch1));   // Output: "1"
        Console.WriteLine(char.IsControl('\t'));        // Output: "True"
        Console.WriteLine(char.IsDigit(ch1));           // Output: "True"
        Console.WriteLine(char.IsLetter(','));          // Output: "False"
        Console.WriteLine(char.IsLower('u'));           // Output: "True"
        Console.WriteLine(char.IsNumber(ch1));          // Output: "True"
        Console.WriteLine(char.IsPunctuation('.'));     // Output: "True"
        Console.WriteLine(char.IsSeparator(str, 4));    // Output: "True"
        Console.WriteLine(char.IsSymbol('+'));          // Output: "True"
        Console.WriteLine(char.IsWhiteSpace(str, 4));   // Output: "True"
        Console.WriteLine(char.Parse("S"));             // Output: "S"
        Console.WriteLine(char.ToLower('M'));           // Output: "m"
        Console.WriteLine('x'.ToString());              // Output: "x"
    }
}
```

### String Creation & Operations

String type in C# represents a sequence of characters in UTF-16 code unit.

```csharp
public class StringSample
{
    private static void Main()
    {
        var chA = 'A';
        string str = "test string";
        System.String str1 = "Hello";
        
        var str2 = new string(chA, 4);
        var str3 = new string(new char[] { 'a', 'b', 'c' });

        Console.WriteLine(str.Length);                  // Output: 11
        Console.WriteLine(str[0]);                      // Output: 't'
        Console.WriteLine(str2);                        // Output: "AAAA"
        Console.WriteLine(str3);                        // Output: "abc"
    }
}
```

- Properties: -

| Property | Description                      | Syntax                                                  |
|----------|----------------------------------|---------------------------------------------------------|
| `Length` | returns the length of the string | `"abc".Length`: returns 3                               |
| `Empty`  | returns an empty string          | `var str = string.Empty` equivalent to `var str = "";`  |

- Member Functions (Methods): -

| Method        | Description                                                                                                                                                                     | Syntax                                        |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| `[i]`         | returns the character at the specified index (i)                                                                                                                                | `"abc"[1]` returns 'b'                        |
| `Concat`      | returns a string resulting from combining two strings                                                                                                                           | `"abc".Concat('def')` returns 'abcdef'        |
| `Replace`     | returns a new string in which all occurrences of a specified Unicode character or String in the current string are replaced with another specified Unicode character or String. | `"abc".Replace('b', 'a')` returns "aac"       |
| `IndexOf`     | returns the index of the first occurence of the specified value, or -1 if it doesn't exist                                                                                      | `"abc".IndexOf('b')` returns 1                |
| `LastIndexOf` | returns the index of the last occurence of the specified value, or -1 if it doesn't exist                                                                                       | `"abbc".LastIndexOf('b')` returns 2           |
| `[i..j]`      | returns an extracted section of the string from i to j                                                                                                                          | `"abbc"[0..2]` returns "ab"                   |
| `Substring`   | returns an extracted section of the string from i to j                                                                                                                          | `"abbc".Substring(0, 2)` returns "ab"         |
| `ToLower`     | returns the lower case version of the string                                                                                                                                    | `"ABC".ToLower()` returns "abc"               |
| `ToUpper`     | returns the upper case version of the string                                                                                                                                    | `"abc".ToUpper()` returns "ABC"               |
| `StartWith`   | returns a boolean determining whether the beginning of this string instance matches the specified string.                                                                       | `"abc".StartWith("ab")` returns true          |
| `EndWith`     | returns a boolean determining whether the end of this string instance matches the specified string.                                                                             | `"abc".EndWith("bc")` returns true            |
| `Split`       | returns a string array that contains the substrings in this instance that are delimited by elements of a specified string or Unicode character array.                           | `"abc".Split('b')` returns ["a", "c"]         |
| `ToCharArray` | returns the characters in this instance to a Unicode character array.                                                                                                           | `"abc".ToCharArray()` returns ['a', 'b', 'c'] |
| `Trim`        | returns a new string in which all leading and trailing occurrences of a set of specified characters from the current string are removed.                                        | `" abc ".Trim()` returns "abc"                |

### Escape Sequences & Verbatim strings

Character combinations consisting of a backslash (\) followed by a letter or by a combination of digits are called "
escape sequences." To represent a newline character, single quotation mark, or certain other characters in a character
constant, you must use escape sequences. An escape sequence is regarded as a single character and is therefore valid as
a character constant.

| Escape sequence | Character name  | Unicode encoding  |
|-----------------|-----------------|-------------------|
| \\'             | Single quote    | 0x0027            |
| \\"             | Double quote    | 0x0022            |
| \\\\            | Backslash       | 0x005C            |
| \0              | Null            | 0x0000            |
| \a              | Alert           | 0x0007            |
| \b              | Backspace       | 0x0008            |
| \f              | Form feed       | 0x000C            |
| \n              | New line        | 0x000A            |
| \r              | Carriage return | 0x000D            |
| \t              | Horizontal tab  | 0x0009            |
| \v              | Vertical tab    | 0x000B            |

We can use the `@` sign in C# to represent a verbatim string which is just a string with no escape sequence except for
the quotes.

```csharp
var str = @"C:\Users\himat";
var str2 = @"Hello, ""Ibrahim""";
```

### string.Format & string interpolation

`string.Format` starts with a format string, followed by one or more objects or expressions that will be converted to
strings and inserted at a specified place in the format string. For example: -

```csharp
decimal temp = 20.4m;
string s = string.Format("The temperature is {0}°C.", temp);
Console.WriteLine(s);
// Displays 'The temperature is 20.4°C.'
```

The {0} in the format string is a format item. 0 is the index of the object whose string value will be inserted at that
position. (Indexes start at 0.) If the object to be inserted is not a string, its ToString method is called to convert
it to one before inserting it in the result string.

Here's another example that uses two format items and two objects in the object list: -

```csharp
string s = string.Format("At {0}, the temperature is {1}°C.", DateTime.Now, 20.4);
Console.WriteLine(s);
// Output similar to: 'At 4/10/2015 9:29:41 AM, the temperature is 20.4°C.'
```

You can have as many format items and as many objects in the object list as you want, as long as the index of every
format item has a matching object in the object list. You also don't have to worry about which overload you call; the
compiler will select the appropriate one for you.

#### Control Formatting

You can follow the index in a format item with a format string to control how an object is formatted. For example, {0:d}
applies the "d" format string to the first object in the object list. Here is an example with a single object and two
format items: -

```csharp
string s = string.Format("It is now {0:d} at {0:t}", DateTime.Now);
Console.WriteLine(s);
// Output similar to: 'It is now 4/10/2015 at 10:04 AM'
```

| Format specifier           | Name                     | Description                                                                                                                                                                                                                                | Examples                                                                                                                                                                                                                                                                                                                        |
|----------------------------|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| "C" or "c"                 | Currency                 | Result: A currency value.<br /><br /> Supported by: All numeric types.<br /><br /> Precision specifier: Number of decimal digits.                                                                                                          | 123.456 ("C", en-US)<br />-> \\$123.46<br /><br /> 123.456 ("C", fr-FR)<br />-> 123,46 &euro;<br /><br /> 123.456 ("C", ja-JP)<br />-> ¥123<br /><br /> -123.456 ("C3", en-US)<br />-> (\\$123.456)<br /><br /> -123.456 ("C3", fr-FR)<br />-> -123,456 &euro;<br /><br /> -123.456 ("C3", ja-JP)<br />-> -¥123.456             |
| "D" or "d"                 | Decimal                  | Result: Integer digits with optional negative sign.<br /><br /> Supported by: Integral types only.<br /><br /> Precision specifier: Minimum number of digits.<br /><br /> Default precision specifier: Minimum number of digits required.  | 1234 ("D")<br />-> 1234<br /><br /> -1234 ("D6")<br />-> -001234                                                                                                                                                                                                                                                                |
| "E" or "e"                 | Exponential (scientific) | Result: Exponential notation.<br /><br /> Supported by: All numeric types.<br /><br /> Precision specifier: Number of decimal digits.<br /><br /> Default precision specifier: 6.                                                          | 1052.0329112756 ("E", en-US)<br />-> 1.052033E+003<br /><br /> 1052.0329112756 ("e", fr-FR)<br />-> 1,052033e+003<br /><br /> -1052.0329112756 ("e2", en-US)<br />-> -1.05e+003<br /><br /> -1052.0329112756 ("E2", fr-FR)<br />-> -1,05E+003                                                                                   |
| "F" or "f"                 | Fixed-point              | Result: Integral and decimal digits with optional negative sign.<br /><br /> Supported by: All numeric types.<br /><br /> Precision specifier: Number of decimal digits.                                                                   | 1234.567 ("F", en-US)<br />-> 1234.57<br /><br /> 1234.567 ("F", de-DE)<br />-> 1234,57<br /><br /> 1234 ("F1", en-US)<br />-> 1234.0<br /><br /> 1234 ("F1", de-DE)<br />-> 1234,0<br /><br /> -1234.56 ("F4", en-US)<br />-> -1234.5600<br /><br /> -1234.56 ("F4", de-DE)<br />-> -1234,5600                                 |
| "P" or "p"                 | Percent                  | Result: Number multiplied by 100 and displayed with a percent symbol.<br /><br /> Supported by: All numeric types.<br /><br /> Precision specifier: Desired number of decimal places.                                                      | 1 ("P", en-US)<br />-> 100.00 %<br /><br /> 1 ("P", fr-FR)<br />-> 100,00 %<br /><br /> -0.39678 ("P1", en-US)<br />-> -39.7 %<br /><br /> -0.39678 ("P1", fr-FR)<br />-> -39,7 %                                                                                                                                               |
| "X" or "x"                 | Hexadecimal              | Result: A hexadecimal string.<br /><br /> Supported by: Integral types only.<br /><br /> Precision specifier: Number of digits in the result string.                                                                                       | 255 ("X")<br />-> FF<br /><br /> -1 ("x")<br />-> ff<br /><br /> 255 ("x4")<br />-> 00ff<br /><br /> -1 ("X4")<br />-> 00FF                                                                                                                                                                                                     |
| Any other single character | Unknown specifier        | Result: Throws a System.FormatException at runtime.                                                                                                                                                                                        |                                                                                                                                                                                                                                                                                                                                 |

#### Control Spacing & Alignment

You can define the width of the string that is inserted into the result string by using syntax such as {0,12}, which
inserts a 12-character string. In this case, the string representation of the first object is right-aligned in the
12-character field. (If the string representation of the first object is more than 12 characters in length, though, the
preferred field width is ignored, and the entire string is inserted into the result string.)

```csharp
var str = string.Format("{0,10} {1,-10}1", "Year", "Month");
Console.WriteLine(str); // Output:      Year Month     1
```

#### The General Rule

```csharp
{index[,alignment][:formatString]}
```

***index***

The zero-based index of the argument whose string representation is to be included at this position in the string. If
this argument is null, an empty string will be included at this position in the string.

***alignment***

Optional. A signed integer that indicates the total length of the field into which the argument is inserted and whether
it is right-aligned (a positive integer) or left-aligned (a negative integer). If you omit alignment, the string
representation of the corresponding argument is inserted in a field with no leading or trailing spaces.

If the value of alignment is less than the length of the argument to be inserted, alignment is ignored and the length of
the string representation of the argument is used as the field width.

***formatString***

Optional. A string that specifies the format of the corresponding argument's result string. If you omit formatString,
the corresponding argument's parameterless ToString method is called to produce its string representation.

#### String interpolation

We can use the dollar sign before a string to interpolate variables into it using the same functionality
that `string.Format` provides.

```csharp
$"{<interpolationExpression>[,<alignment>][:<formatString>]}"
```

Here an example of how we can accomplish something like that: -

```csharp
var salary = 1531.323;
var str = $"{salary,10:F2}";

Console.WriteLine($"{"Salary",10}");
Console.WriteLine(str);

// Output:
//    Salary
//   1531.32
```