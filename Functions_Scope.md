**To see the code block examples in this tutorial along with more, run the contents of [Functions_Scope.playground](Functions_Scope.playground).**

# Functions

Functions are blocks of code that can be called by a name to perform specified tasks and typically are meant to be used repeatedly in a program.

## Syntax

To define a new function, beging with the reserved word `func`, followed by the name of your function. Then, declare uniquely-named parameters separated by commas and in a set of parentheses. If you return a value, include an arrow `->` with the type of value your function returns. Surround the function's code with curly brackets.

To call the function in the body of the code, reference the name of the function and pass the appropriate arguments with parentheses. The first argument can be sent in by value, but the subsequent arguments must also reference the name of the parameter in the function definition with a colon and then the value to pass in. Even though the name of the parameter is specified, the arguments must be presented in order. If you do not want to call the parameters every time you call the function, type and underscore `_` followed by a space before the name of the parameter in the function definition.

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

## Parameters

In Swift, functions can have no inputs or as many inputs as needed. The inputs, known as parameters, have to have type declarations, and any arguments you pass to the function in your code must match the parameter types declared. Parameters are taken in as constants, so you can access them in the function but you cannot change them. To modify the value of a parameter, you must create a variable holding its value.

Parameters can have internal names and external names. Internal names are used inside the function code, and external names are used when you call the function. When defining a function and its parameters, precede the local parameter name with the external parameter name. The local parameter name is followed by a colon as normal and the type of the value. The benefit of using an external name is that it can make your code more readable, especially if the function takes several arguments.

```swift
// using an external parameter name
func count(from n: Int, to m: Int, by o: Int){
    for(var i=n; i<m; i++){
        if(i%o==0){
            print(i)
        }
    }
}

count(from: 4, to: 16, by: 3)
```

Parameters in Swift can take default values if no input is provided. When you declare the parameter's type in the function definition, follow it with an equal sign and its default value. Functions can also have variadic parameters, which takes zero or more values of the same type. This is taken in as an array, so the values are indexed. To make a parameter variadic, follow its type declaration with an ellipsis `...`.

```swift
// variadic and default parameters
func count(n: Int..., m: Int = 1){
    for _ in 1...m{
        for num in n{
            print(num)
        }
    }
}

count(10,9,8, m: 2)
```

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

## Return Values

Functions can have no return values or one return value. Like parameters, the return value must have a type declaration, if you catch a return value with a variable or by funneling into another function, the types have to match. To return more than one value, you can pass values as a tuple, in which case, the return type would be in tuple format with variable names and types for each one.

```swift
// I want to return multiple things!!!!
func word(n: String) -> (first: Character, last: Character, len: Int){
    let f = n[n.startIndex]
    let l = n[n.endIndex.predecessor()]
    let len = n.characters.count
    return(f,l,len)
}

let w = word("Super")
print("The first letter of this word is \(w.first). The last is \(w.last). It is \(w.len) letters long.")
```

## Function Types

Functions in Swift have types, made of its parameter types and return type. A function's type is written in this format: `(parameter type, parameter type, etc...) -> return type`. If a function takes two integers as arguments and returns a boolean, its type is `(Int, Int) -> Bool`. If it doesn't take any arguments and doesn't return any values, its type is `() -> Void`.

Functions' having types is useful because it allows you to pass a function as an argument into another function or to return a function from a function.

```swift
// getting meta w functions and passing them as arguments
func half(j: Double) -> Double{
    return j/2
}
func printHalf(half: (Double) -> Double, i: Double){
    print(half(i))
}

printHalf(half, i: 45)
```

## Nested and Recursive Functions

Functions can be defined inside of other functions. Those inner functions are *nested* and are only available inside the function(s) they are defined in--they do not have global scope.

Similarly, you can call a function in itself. This is recursion. Call it the same way you would call a different function.

```swift
//recursion
func makeZero(number: Int){
    var i = number
    if i < 0{
        i += 1
        makeZero(i)
    }
    else if i > 0 {
        i -= 1
        makeZero(i)
    }
    else{
        print(i)
    }
}

makeZero(5)
```

# Variable Scope

## Loops

Variables created in a loop have scope limited to that loop, so if you declare a variable in the body of your code, then declare a variable of the same name inside a loop, you now have two variables of the same name.

```swift
// variable in a loop
var b = "b"
//prints b
print("before loop, b = : \(b)")
if(3<4){
    var b = "abc"
    //prints abc
    print("in loop, b = : \(b)")
}
//prints b
print("after loop, b = : \(b)")
```

## Functions

Functions cannot access any values declared outside of it. By default, the value of a variable outside of a function remains unchanged in the body/global scope of the program if passed to a function. Likewise, variables in a function have scope limited to that function.

For a function to change a value in the body of a program, you can add the reserved word `inout` and a space in front of the parameter name in the function definition. In the body of the code where you call the function, place an ampersand `&` in front of the argument without a space.

```swift
// in-out parameters
func changeLetter(inout d: String) -> String{
    d = "d"
    print("in function, d = : \(d)")
    return(d)
}
var c = "c"
//prints c
print("before function, c = : \(c)")
changeLetter(&c)
print("after function, c = : \(c)")
```

## Global Variables

Global variables in Swift are those that are declared outside of any function, method, closure, or type context. There is no keyword or reserved word used to write a global variable.

## Passing by Value/Reference

Swift passes by value.

```swift
// passing by value
var d = ["c","a","t"]
var e = ["d","o","g"]
d=e
e[1] = "u"
for dd in d{
    print(dd)
    // prints dog
}
for ee in e{
    print(ee)
    // prints dug
}
```

# Sources

Andy Bargh http://andybargh.com/lifetime-scope-and-namespaces-in-swift/#Scope Accessed 24 Mar. 2016

Facets of Swift, Part 3: Values and References https://medium.com/swift-programming/facets-of-swift-part-3-values-and-references-d2aac239d6f4#.4hbpnd4fg Accessed 24 Mar. 2016

iOS Developer Library https://developer.apple.com/library/ios/documentation/Swift/Conceptual/Swift_Programming_Language/Functions.html#//apple_ref/doc/uid/TP40014097-CH10-ID158 Accessed 24 Mar. 2016

We Heart Swift https://www.weheartswift.com/recursion/ Accessed 24 Mar. 2016
