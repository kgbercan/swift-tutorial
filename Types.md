# Variables and Constants

## Declaration

Swift uses **variables** to hold values that can change throughout your program and **constants** to hold values that cannot change once set. To distinguish between these two, Swift requires declaring which one the value is--use `var` to declare a variable and `let` to declare a constant.

While it is necessary to declare variable or constant, it is not necessary to declare a type; Swift is not strongly-typed and infers from the value given what its type is. However, Swift *is* type-safe, so a variable of one type can only hold data of that type. You may choose to specify which type the variable or constant can hold by using a **type annotation**. After the variable or constant name, type a colon, a space, and the type.

To change the type of a variable, enclose it in parentheses and precede it with the desired type, like this: `String(40)`. If you perform a narrowing conversion and convert a `Double` to an `Int`, the value is rounded to its floor--`Int(5.89)` is 5 and `Int(-2.8)` is -2. If you combine an `Int` and a floating-point number in Swift, you do not have to "manually" convert it; the result is inferred to be a `Double`, which is a widening conversion.

```swift
// simply declare a variable/constant
let prop: String
let maximum

// initialize a variable/constant
var count: Int = 1
var favColor = "yellow"

// not okay and will return errors
favColor = count
count = 1.2

x = "5" + 6


```

Swift is statically-typed, so types are checked at compile time.

## Naming

Swift allows almost any character to be used in naming a variable/constant, including Unicode characters and emojis. Some invalid characters are whitespaces, mathematical symbols, arrows, private-use (or invalid) Unicode code points, or line- and box-drawing characters. You may use numbers, as long as it is not the first character in the name. The compiler checks that the convention of a variable name beginning with a letter (or an emoji) is met. It is frowned upon to use reserved Swift keywords as variable/constant names, but it is possible if you surround the name with back ticks. Naming conventions in the community dictate that variable, constant, and function names should begin with a lowercase letter and that class names should begin with an uppercase letter.

# Types

## Data Types

- Integer: a signed or unsigned whole number; follows the following naming convention example: an 8-bit unsigned number is declared `UInt8` and a 32-bit signed number is declared `Int32`.

  * `Int`: the Integer type with the same word-size as your machine; the default that Swift assigns to an integer, so you don't have to declare what size you want to use or worry about signs
  * `UInt`: the unsigned option of `Int`; the use of this one is discouraged--just use `Int`! You'll avoid ever having to convert your numbers, and other headaches.

- Floating-point number: a number with a fraction, or a decimal

  * `Double`: 64-bit representation; used as the default floating-point number insead of `Float`
  * `Float`: 32-bit representation; should not really be used unless a `Double` for some reason is less-preferred

- Boolean value: `Bool`; holds `true` or `false`
- Tuple: multiple values of any data type (which can vary from each other) presented as one unit

  * Surrounded by parentheses and separated by commas
  * Data type declared using each component's type, *not* by a general type called Tuple (which does not exist)
  * Best used for storing temporary values and returning multiple values from a function
  * Can be *decomposed* as follows:
  
  ```swift
  // decompose a tuple by naming each component
  var dog = ("Fluffy", "female", 2)
  var (name, sex, age) = dog
  print(name)
  print(sex)
  print(age)
  
  // alternative way to name a tuple
  let size = (letter: "M", number: 8)
  print(size.letter)
  print(size.number)
  
  // decompose a tuple by naming only the component you need
  let areaCode = (617, "Boston")
  let (_, city) = areaCode
  print(city)
  
  // decompose a tuple by indexing
  var height = (5,8)
  print(height.0) // outputs 5
  print(height.1) // outputs 8
  ```
  
- Optional: denoted by `?` after the data type declaration; the *name* of this type an *optional*. (While it is your choice to use it, I'm not trying to say that it is optional to be used.)

  * Used in cases where you aren't sure if the value you will assign to your variable will be the right one
  * Occurs when you try to assign a value to a variable or constant by converting it from one data type to another
  * Allows the variable to either take a value of a specified data type or to take the value `nil`
  * Can be inferred, meaning you do not have to go out of your way to use it
  * If you will set a variable to `nil` in the future, declare its type followed by `?`
  
  ```swift
  var a = "1"
  var y = Int(a)
  // prints "1"
  print(y)
  
  var b = "b"
  var z = Int(b)
  // prints "nil"
  print(z)
  
  var c: Bool? = false
  c = true
  c = nil
  
  // not possible and will return an error
  var b = nil
  ```

## Value Types

Value types used in Swift are:

- `String`: textual data surrounded by quotation marks

  * Initialize an empty `String` by declaring a variable/constant and setting it to either `String()` or `""`
  * Check if a `String` is empty using the `isEmpty` property which returns a Boolean
  * You *cannot* access a `String`s individual characters by indexing with a number
  * Walk through a `String` using a `for-in` loop and the `String`s property `characters`

- `Character`: a single character in quotation marks initialized by declaring a variable/constant as a `Character` type

  * Make up a `String`
  * An array of `Character` values can be cast as a `String` to become a cohesive string

## Collection Types

Can you put different data types in the same array or list?

- *Array*:
- *Set*:
- *Dictionary*:



## Concatenation and Interpolation

### Concatenation

`String`s can be combined using a plus sign, and a `Character` can be added to a `String` using the `String`s `append()` method. `Character`s cannot be appended to because by definition they are single-character values.

### Interpolation

String interpolation is creating a String value from values of various types. Instead of casting with `String()` and combining it with another `String` using a plus sign, you can refer to the variable or constant by its name, surround it with parentheses, and preceed it with a backslash `\` in the *same* string literal as the rest of your text:

```swift
let val1 = 5
let val2 = 6
let x = val1+val2

// interpolation
var expr = "\(val1) + \(val2) is \(x)."

// casting and concatentation
expr = String(val1) + " + " + String(val2) + " is " + String(x) + "."
```

# Source

iOS Developer Library https://developer.apple.com/library/ios/documentation/Swift/Conceptual/Swift_Programming_Language/TheBasics.html#//apple_ref/doc/uid/TP40014097-CH5-ID309 Accessed 10 Feb. 2016
