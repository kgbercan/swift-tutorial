**To see some of the code block examples in this tutorial along with more, run the contents file of [ControlFlow.playground](ControlFlow.playground).**

# Conditionals

Conditional statements execute code once if a condition is met or different code if the condition is not met.

## If/Else If/Else

`If` statements are made with the `if` reserved word followed by a condition with the associated code in curly brackets after it. Optionally, and as good programming practice, you can have an `else` statement after, which is a catch-all in the case that the condition is not met. You write the reserved word `else` and simply follow with the code to be executed in curly brackets. But say you don't have only 2 outcomes--there 3 or 4 cases, or even more: follow your `if` block with `else if`*condition* `{` *code to be executed* `}`. You can have an unlimited number of these.

You can have an `if` statement by itself, but not an `else if` and not an `else`. Further, you must surround the code to be executed with curly brackets; otherwise, the `if`/`else if`/`else` statement does not compile and run. This prevents the "dangling else" problem that some languages have where it becomes unclear what code goes with which nested sets of `if` statements.

```
var temp = 50
if temp <= 40 {
    print("It's cold. You should wear a scarf.")
}
else if 40 < temp && temp <= 55 {
    print("It's not too cold out, but wear a jacket.")
}
else {
    print("It's warm!")
}
```

## Switch

`Switch` statements do the same work as a bunch of `if`/`else if` statements, but more cleanly. It checks a given input for matches, or cases, and then executes the code under the appropriate case.

To write a `switch` statement, begin with the reserved word `switch` followed by a value which you are considering. Type an opening curly bracket, and list the cases. To define a case, use the reserved word `case` and follow with a value to be matched, then a colon. Indented on the next line, provide the code to be executed if that value is matched by the given considered value. You can have as many cases as you'd like, as long as each one has code; you may not leave a case empty. At the end, since it is practically impossible to consider each and every potential case, use the reserved word `default` with a colon to provide code to be executed if none of the values above match. The `default` block is not necessary, but is recommended. Close the cases with a closing curly bracket.

In Swift, there is no fallthrough like in some other languages, where if a condition is met for one case and you do not exit it properly, all of the consequent cases are also executed. Thus, in Swift, there is no need to use a `break` to exit a case, as it happens implicitly. If you would like fallthrough to occur, Swift has given us the gift of `fallthrough`, a reserved word you can add to any case to perform the next case, as well. If you want it to fall through all the way through the default, you have to put `fallthrough` in each case.

```swift
var state = "MA"

// because I put fallthrough in the last two cases, this will print:
//     New England
//     New England is the best region in the country.
//     I was too lazy to type all the abbreviations. Sorry.

switch state{
case "IL","IN","MI","OH","WI","IA","KS","MN","MO","NE","ND","SD":
    print("Midwest")
case "NJ","NY","PA", "RI":
    print("Middle Atlantic")
case "CT","ME","MA","NH","VT":
    print("New England")
    fallthrough
case "Somewhere in New England":
    print("New England is the best region in the country.")
    fallthrough
default:
    print("I was too lazy to type all the abbreviations. Sorry.")
}
```

Additionally, Swift's `switch` statements have the reserved word `where`. It can be used to check for additional conditions. Apple's documentation (which can be accessed in the source at the very end of this document) gives a lovely example:

```swift
let yetAnotherPoint = (1, -1)
switch yetAnotherPoint {
case let (x, y) where x == y:
    print("(\(x), \(y)) is on the line x == y")
case let (x, y) where x == -y:
    print("(\(x), \(y)) is on the line x == -y")
case let (x, y):
    print("(\(x), \(y)) is just some arbitrary point")
}
```

## Guard

`Guard` is an alternative to an `if` statement to use when you know you will need a control transfer statement or when you will redirect to a function. It is written with the reserved word `guard` followed by variable/constant with a boolean value, then the reserved word `else` with code to be executed in curly brackets. It seems to be particularly useful when throwing errors, and since I am not discussing error handling just yet, I cannot give a pertinent example of a `guard` statement. However, Natasha The Robot writes a compelling argument for using `guard` instead of `if` and shows simple code to demonstrate [here] (https://www.natashatherobot.com/swift-2-error-handling/) and [here] (https://www.natashatherobot.com/swift-guard-better-than-if/).

# Loops

Loops *loop* through code--they execute the same chunk of statements over and over until a condition is met.

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

var m = 0
for m = 0; m < 500; m += 50{
    print("We are in the sprint\n\n")
}
print("Good job--you sprinted your last \(m) meters.")
```

## While

A `while` loop performs a code block until a given condition is no longer true. It is a good alternative to a `for` loop if you do not know when the condition will change. Swift has two kinds of `while` loops: `while`, which checks the condition at the start of each loop, and `repeat-while`, which checks the condition at the end of each loop. `Repeat-while` is useful if you want the code in the loop to execute at least once. With both of these, be careful not to get yourself into an infinite loop--if you don't change the condition inside the loop, you will get stuck.

To write a while loop, start with the reserved word `while` and follow with the condition, then an opening curly bracket, the code to loop over, and a closing curly bracket to signify the end of the loop. To write a `repeat-while` loop, use the reserved word `repeat`, follow with your code in curly brackets, and add the `while` condition to the end.

```swift
var allergic = true
while allergic{
    print("You can't get a cat if you are allergic!")
    allergic = false
}

repeat{
    print("I thought you were allergic to cats...")
    allergic = true
} while !allergic
```

# Control Transfer Statements

Control transfer statements redirect the flow of execution to a different point in the code. Swift has `continue`, `break`, `fallthrough`, `return`, and `throw`. `Fallthrough` was discussed above in the `switch` section, so I'll skip it here, and `return` and `throw` are more relevant when considering functions, so I will save that for a future discussion.

## Continue

The `continue` statement tells a loop to leave the iteration it is in and to start over with the next iteration. It is only allowed inside of a loop.

```swift
var reps = 10;
while reps < 15{
    reps++
    
    // on number 13, the continue statement will bring us back to the top of the loop
    // so it will not print reps for 13, it will go to 14
    
    if reps == 13{
        print("I want to skip this one")
        continue
    }
    print(reps)
}
```

## Break

`Break` tells the program to leave the code that it is in entirely. It can be useful in a loop if you think you may get stuck in an infinite loop, or if there may be a condition where you will want to exit the loop. Many programmers do not agree with the use of `break` for this purpose, but you can do whatever you want because it's your code and no one can tell you how to live your life. `Break` is especially useful in a `switch` block if you want to specify a case but don't have any code for it and you just want it to be ignored.

```swift
let age = 13
switch age{
case 5...11:
    print("You are in elementary school.")
case 12...17:
    // teenagers are hard to talk to
    break
case 18...25:
    print("You may be persuing higher education")
default:
    print("You are likely not in school anymore.")
}
```

# Things to Keep in Mind

- Any variables or constants initialized inside of a loop or a conditional statement is limited in scope to that block. I.e., if you initialize a variable inside of an `if` statement, or a `while` loop, or any of the control flow structures I just taught you about, you cannot access that variable outside of the block where you initialized it.
- Short-circuit logic is not supported in Swift. This means if you are considering two conditions (or more) and one of them is completely not okay, like division by zero, even if that condition is not checked (say the first condition is perfectly reasonable, like division by 1, and it is and *or* situation), Swift throws an error. In some languages, illogical code can remain in the program and as long as it isn't checked, there will be no problem. Example:
```swift
var height = 70
var weight = 170
if height/12 >= 6 || weight/0 == 100{
    print("You will never get to this point because you cannot divide by zero and Swift is mad at you for trying.")
}
```

# Source

iOS Developer Library https://developer.apple.com/library/ios/documentation/Swift/Conceptual/Swift_Programming_Language/ControlFlow.html#//apple_ref/doc/uid/TP40014097-CH9-ID120 Accessed 29 Feb. 2016

Natasha the Robot https://www.natashatherobot.com/swift-2-error-handling/ Accessed 29 Feb. 2016
