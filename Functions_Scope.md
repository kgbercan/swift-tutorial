# Functions

Functions are blocks of code that can be called by a name to perform specified tasks and typically are meant to be used repeatedly in a program. Functions in Swift have a type, made of its parameter types and return type, meaning you can use a function as an input parameter for another function.

## Parameters and Return Values

In Swift, functions can have no inputs, no return values, or as many inputs or return values as needed. The inputs, otherwise known as parameters, and return values have to have type declarations, and any arguments you pass to the function in your code must match the parameter types declared. Likewise, if you catch the return values with a variable or by funneling into another function, the types have to match.

Functions with different numbers of parameters or with different parameter types can have the same name, but otherwise, they must be uniquely named. For example, you can write two function called `cat()` if one takes an `int` as a parameter and the other takes a `String`, but you cannot have two `cat()` functions that both take a `String`.

## Syntax

To define a new function, beging with the reserved word `func`, followed by the name of your function. Then, send in your arguments in parentheses and separated by commas; the first argument can be sent in by value, but any subsequent arguments have to have the name of the parameter for the function. If you have to return a value, an arrow `->` with the type of value your function returns. Surround the function's code with curly brackets.

To call your function in the body of your code, reference the name of the function and pass the appropriate arguments with parentheses.

```swift

```

Are there any rules about where the function has to be placed in your code file so that it can run
(i.e., before main, after main, in the same file, in the same folder, etc)?

## Recursion


# Variabe Scope

## Loops

Declare a variable (say, x) in the main body of your program. Then declare a variable of the
same name inside of a loop. Is there a conflict? Is the old variable overwritten, or do you now
have two variables of the same name?

## Functions

## Global Variables

## Passing by Value/Reference

(Hint: write a function that alters its input, but doesn't return it. Pass it a variable, and see if
the alteration is visible in main after you call the function)

If you run this code (or the equivalent) in your language, what is the output? What does that tell
you about how the language handles assignments?
char [] a = {'c','a','t'}
char [] b = {'d','o','g'}
a=b
b[1] = 'u'
print a
print b


# Source

iOS Developer Library https://developer.apple.com/library/ios/documentation/Swift/Conceptual/Swift_Programming_Language/ControlFlow.html#//apple_ref/doc/uid/TP40014097-CH9-ID120 Accessed 29 Feb. 2016

