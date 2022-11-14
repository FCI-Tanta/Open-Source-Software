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
// 012
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
        var array3 = { 1, 2, 3, 4, 5, 6 };

        // Declare a two dimensional array.
        var multiDimensionalArray1 = new int[2, 3];

        // Declare and set array element values.
        var multiDimensionalArray2 = { { 1, 2, 3 }, { 4, 5, 6 } };

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
- For value types, the array elements are initialized with the default value, the 0-bit pattern; the elements will have the value 0.
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