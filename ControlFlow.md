# Conditionals

## If

short-circuit evaluation
“dangling else"

## Guard

## Switch
no fall through

# Loops

## For-in

A `for-in` loop runs a block of code for each item in a sequence. To use one, begin with the reserved word `for`, follow with a variable name or an underscore `_` (only if you don't need to access the value), `in`, and a range. The variable does not have to be declared, as it is implied in the `for-in` loop. If you want to walk through the length of an array or dictionary, you can refer to the name of the array/dictionary instead of providing a range. The block of code to be performed in the range should be enclosed in curly brackets.

```swift
// ... is the closed range operator, so "Betelgeuse" will print 3 times
for _ in 1...3{
   print("Betelgeuse")
}

var alpha = ["A","B","C","D"]
for letter in alpha{
   print(letter)
}
```

## For

A `for` loop runs a block of code until a condition is met, usually by incrementing a counter in the loop. The structure of a `for` loop is: `for` *initialization*; *condition*; *increment*`{` *code to be performed each time* `}`. The code inside the curly brackets is executed until the condition is met, and any variables/constants declared in the `for` loop have a scope limited to the loop. To access the values outside of the loop, they must have been declared before the loop.

```swift
// these for loops row crew

for var meters = 0; meters < 2000; meters += 10{
   print("Legs, body, arms\nArms, body, legs\n\n")
}

var m
for m = 0; m < 500; m += 50{
   print("We are in the sprint\n\n"
}
print("Good job--you sprinted your last \(m) meters.")
```

## While

break, continue: transfer the flow of execution to another point in your code

anything like Perl's “unless” ?

# Source

iOS Developer Library https://developer.apple.com/library/ios/documentation/Swift/Conceptual/Swift_Programming_Language/ControlFlow.html#//apple_ref/doc/uid/TP40014097-CH9-ID120 Accessed 29 Feb. 2016
