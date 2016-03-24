# Functions

Functions are blocks of code that can be called by a name to perform specified tasks and typically are meant to be used repeatedly in a program. Functions in Swift have a type, made of its parameter types and return type.

## Syntax

To define a new function, beging with the reserved word `func`, followed by the name of your function. Then, declare uniquely-named parameters separated by commas and in a set of parentheses. If you return a value, include an arrow `->` with the type of value your function returns. Surround the function's code with curly brackets.

To call the function in the body of the code, reference the name of the function and pass the appropriate arguments with parentheses. The first argument can be sent in by value, but the subsequent arguments must also reference the name of the parameter in the function definition with a colon and then the value to pass in. Even though the name of the parameter is specified, the arguments must be presented in order. Also, the function must be defined before it is called in code.

```swift
// this function squares an Int and returns an Int
func square(num: Int) -> Int{
    return(num*num)
}

var a = square(2)
print(a)
a = square(a)
print(a)


// this function takes two Strings and does not have a return value
func intro(friend1: String, friend2: String){
    print("\(friend1), this is \(friend2).")
}

intro("Adele", friend2: "Justin")
```

## Parameters and Return Values

In Swift, functions can have no inputs or as many inputs as needed. The inputs, known as parameters, have to have type declarations, and any arguments you pass to the function in your code must match the parameter types declared. Parameters are taken in as constants, so you can access them in the function but you cannot change them. To modify the value of a parameter, you must create a variable with its value.

Functions with different numbers of parameters or with different parameter types can have the same name, but otherwise, they must be uniquely named. For example, you can write two function called `cat()` if one takes an `Int` as a parameter and the other takes a `String`, but you cannot have two `cat()` functions that both take a `String`.

```swift
// two functions with the same name but different types
func type(c: Int){
    print("The argument is an Int.")
}

func type(c: String){
    print("The argument is a String.")
}

type(1)
type("1")
```

Functions can have no return values or one return value. Like parameters, the return value must have a type declaration, if you catch a return value with a variable or by funneling into another function, the types have to match. To return more than one value, you can pass values as a tuple, in which case, the return type would be in tuple format with variable names and types for each one.

```swift

```

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

