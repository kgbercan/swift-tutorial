# Conditionals

## If

short-circuit evaluation
“dangling else"

## Guard

## Switch
no fall through

# Loops

## For-in
A for-in loop runs a block of code for each item in a sequence. To use one, begin with the reserved word `for`, follow with a variable name or an underscore `_` (only if you don't need to access the value), `in`, and a range. The variable does not have to be declared, as it is implied in the for-in loop. If you want to walk through the lenght of an array or dictionary, you can refer to the name of the array/dictionary instead of providing a range. The block of code to be performed in the range should be enclosed in curly brackets.

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
A for loop runs a block of code until a condition is met, usually by incrementing a counter in the loop.


## While

break, continue: transfer the flow of execution to another point in your code

anything like Perl's “unless” ?

