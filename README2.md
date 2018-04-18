JavaScript
This part of the JavaScript section on MDN serves as a repository of facts about the JavaScript language. Read more about this reference.

Global Objects
This chapter documents all the JavaScript standard built-in objects, along with their methods and properties.

Value properties
These global properties return a simple value; they have no properties or methods.

Infinity
NaN
undefined
null literal
Function properties
These global functions—functions which are called globally rather than on an object—directly return their results to the caller.

eval()
uneval()
isFinite()
isNaN()
parseFloat()
parseInt()
decodeURI()
decodeURIComponent()
encodeURI()
encodeURIComponent()
escape()
unescape()
Fundamental objects
These are the fundamental, basic objects upon which all other objects are based. This includes objects that represent general objects, functions, and errors.

Object
Function
Boolean
Symbol
Error
EvalError
InternalError
RangeError
ReferenceError
SyntaxError
TypeError
URIError
Numbers and dates
These are the base objects representing numbers, dates, and mathematical calculations.

Number
Math
Date
Text processing
These objects represent strings and support manipulating them.

String
RegExp
Indexed collections
These objects represent collections of data which are ordered by an index value. This includes (typed) arrays and array-like constructs.

Array
Int8Array
Uint8Array
Uint8ClampedArray
Int16Array
Uint16Array
Int32Array
Uint32Array
Float32Array
Float64Array
Keyed collections
These objects represent collections which use keys; these contain elements which are iterable in the order of insertion.

Map
Set
WeakMap
WeakSet
Vector collections
SIMD vector data types are objects where data is arranged into lanes.

SIMD
SIMD.Float32x4
SIMD.Float64x2
SIMD.Int8x16
SIMD.Int16x8
SIMD.Int32x4
SIMD.Uint8x16
SIMD.Uint16x8
SIMD.Uint32x4
SIMD.Bool8x16
SIMD.Bool16x8
SIMD.Bool32x4
SIMD.Bool64x2
Structured data
These objects represent and interact with structured data buffers and data coded using JavaScript Object Notation (JSON).

ArrayBuffer
SharedArrayBuffer
Atomics
DataView
JSON
Control abstraction objects
Promise
Generator
GeneratorFunction
AsyncFunction
Reflection
Reflect
Proxy
Internationalization
Additions to the ECMAScript core for language-sensitive functionalities.

Intl
Intl.Collator
Intl.DateTimeFormat
Intl.NumberFormat
WebAssembly
WebAssembly
WebAssembly.Module
WebAssembly.Instance
WebAssembly.Memory
WebAssembly.Table
WebAssembly.CompileError
WebAssembly.LinkError
WebAssembly.RuntimeError
Other
arguments
Statements
This chapter documents all the JavaScript statements and declarations.

For an alphabetical listing see the sidebar on the left.

Control flow
Block
A block statement is used to group zero or more statements. The block is delimited by a pair of curly brackets.
break
Terminates the current loop, switch, or label statement and transfers program control to the statement following the terminated statement.
continue
Terminates execution of the statements in the current iteration of the current or labeled loop, and continues execution of the loop with the next iteration.
Empty
An empty statement is used to provide no statement, although the JavaScript syntax would expect one.
if...else
Executes a statement if a specified condition is true. If the condition is false, another statement can be executed.
switch
Evaluates an expression, matching the expression's value to a case clause, and executes statements associated with that case.
throw
Throws a user-defined exception.
try...catch
Marks a block of statements to try, and specifies a response, should an exception be thrown.
Declarations
var
Declares a variable, optionally initializing it to a value.
let
Declares a block scope local variable, optionally initializing it to a value.
const
Declares a read-only named constant.
Functions and classes
function
Declares a function with the specified parameters.
function*
Generator Functions enable writing iterators more easily.
async function
Declares an async function with the specified parameters.
return
Specifies the value to be returned by a function.
class
Declares a class.
Iterations
do...while
Creates a loop that executes a specified statement until the test condition evaluates to false. The condition is evaluated after executing the statement, resulting in the specified statement executing at least once.
for
Creates a loop that consists of three optional expressions, enclosed in parentheses and separated by semicolons, followed by a statement executed in the loop.
for each...in
Iterates a specified variable over all values of object's properties. For each distinct property, a specified statement is executed.
for...in
Iterates over the enumerable properties of an object, in arbitrary order. For each distinct property, statements can be executed.
for...of
Iterates over iterable objects (including arrays, array-like objects, iterators and generators), invoking a custom iteration hook with statements to be executed for the value of each distinct property.
while
Creates a loop that executes a specified statement as long as the test condition evaluates to true. The condition is evaluated before executing the statement.
Others
debugger
Invokes any available debugging functionality. If no debugging functionality is available, this statement has no effect.
export
Used to export functions to make them available for imports in external modules, another scripts.
import
Used to import functions exported from an external module, another script.
label
Provides a statement with an identifier that you can refer to using a break or continue statement.
with
Extends the scope chain for a statement.
Expressions and operators
This chapter documents all the JavaScript expressions and operators.

For an alphabetical listing see the sidebar on the left.

Primary expressions
Basic keywords and general expressions in JavaScript.

this
The this keyword refers to the function's execution context.
function
The function keyword defines a function expression.
class
The class keyword defines a class expression.
function*
The function* keyword defines a generator function expression.
yield
Pause and resume a generator function.
yield*
Delegate to another generator function or iterable object.
async function*
The async function defines an async function expression.
await
Pause and resume an async function and wait for the promise's resolution/rejection.
[]
Array initializer/literal syntax.
{}
Object initializer/literal syntax.
/ab+c/i
Regular expression literal syntax.
( )
Grouping operator.
Left-hand-side expressions
Left values are the destination of an assignment.

Property accessors
Member operators provide access to a property or method of an object
(object.property and object["property"]).
new
The new operator creates an instance of a constructor.
new.target
In constructors, new.target refers to the constructor that was invoked by new.
super
The super keyword calls the parent constructor.
...obj
Spread syntax allows an expression to be expanded in places where multiple arguments (for function calls) or multiple elements (for array literals) are expected.
Increment and decrement
Postfix/prefix increment and postfix/prefix decrement operators.

A++
Postfix increment operator.
A--
Postfix decrement operator.
++A
Prefix increment operator.
--A
Prefix decrement operator.
Unary operators
A unary operation is operation with only one operand.

delete
The delete operator deletes a property from an object.
void
The void operator discards an expression's return value.
typeof
The typeof operator determines the type of a given object.
+
The unary plus operator converts its operand to Number type.
-
The unary negation operator converts its operand to Number type and then negates it.
~
Bitwise NOT operator.
!
Logical NOT operator.
Arithmetic operators
Arithmetic operators take numerical values (either literals or variables) as their operands and return a single numerical value.

+
Addition operator.
-
Subtraction operator.
/
Division operator.
*
Multiplication operator.
%
Remainder operator.
**
Exponentiation operator.
Relational operators
A comparison operator compares its operands and returns a Boolean value based on whether the comparison is true.

in
The in operator determines whether an object has a given property.
instanceof
The instanceof operator determines whether an object is an instance of another object.
<
Less than operator.
>
Greater than operator.
<=
Less than or equal operator.
>=
Greater than or equal operator.
Note: => is not an operator, but the notation for Arrow functions.

Equality operators
The result of evaluating an equality operator is always of type Boolean based on whether the comparison is true.

==
Equality operator.
!=
Inequality operator.
===
Identity operator.
!==
Nonidentity operator.
Bitwise shift operators
Operations to shift all bits of the operand.

<<
Bitwise left shift operator.
>>
Bitwise right shift operator.
>>>
Bitwise unsigned right shift operator.
Binary bitwise operators
Bitwise operators treat their operands as a set of 32 bits (zeros and ones) and return standard JavaScript numerical values.

&
Bitwise AND.
|
Bitwise OR.
^
Bitwise XOR.
Binary logical operators
Logical operators are typically used with boolean (logical) values, and when they are, they return a boolean value.

&&
Logical AND.
||
Logical OR.
Conditional (ternary) operator
(condition ? ifTrue : ifFalse)
The conditional operator returns one of two values based on the logical value of the condition.

Assignment operators
An assignment operator assigns a value to its left operand based on the value of its right operand.

=
Assignment operator.
*=
Multiplication assignment.
/=
Division assignment.
%=
Remainder assignment.
+=
Addition assignment.
-=
Subtraction assignment
<<=
Left shift assignment.
>>=
Right shift assignment.
>>>=
Unsigned right shift assignment.
&=
Bitwise AND assignment.
^=
Bitwise XOR assignment.
|=
Bitwise OR assignment.
[a, b] = [1, 2]
{a, b} = {a:1, b:2}
Destructuring assignment allows you to assign the properties of an array or object to variables using syntax that looks similar to array or object literals.

Comma operator
,
The comma operator allows multiple expressions to be evaluated in a single statement and returns the result of the last expression.
Non-standard features
Legacy generator function
The function keyword can be used to define a legacy generator function inside an expression. To make the function a legacy generator, the function body should contains at least one yield expression.
Expression closures
The expression closure syntax is a shorthand for writing simple function.
[for (x of y) x]
Array comprehensions.
(for (x of y) y)
Generator comprehensions.
Functions
This chapter documents how to work with JavaScript functions to develop your applications.

arguments
Arrow functions
Default parameters
Rest parameters
Additional reference pages
Lexical grammar
Data types and data structures
Strict mode
Deprecated features
