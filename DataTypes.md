# Variables and Constants

## Data Types

Data types used in Swift are:

- *Int*: integers
- *Double*
- *Float*: floating-point values
- *Bool*: Boolean values
- *String*: textual data
- *Tuple*:

## Declaration

Swift uses *variables* to hold data that can change throughout your program and *constants* to hold data that cannot change once set. To distinguish between these two, Swift requires declaring which one the data is--use `var` to declare a variable and `let` to declare a constant.

While it is necessary to declare variable or constant, it is not necessary to declare a data type; Swift is not strongly typed and infers from the data given what its type is. However, Swift *is* type-safe, so a variable of one data type can only hold data of that data type. If you do not assign a value to a declared variable or constant, you may choose to specify which data type the variable or constant can hold by using a **type annotation**. After the variable or constant name, type a colon, a space, and the data type.

## Naming

Swift allows almost any character to be used in naming a variable/constant, including Unicode characters and emojis. Some invalid characters are whitespaces, mathematical symbols, arrows, private-use (or invalid) Unicode code points, or line- and box-drawing characters. You may use numbers, as long as it is not the first character in the name. It is frowned upon to use reserved Swift keywords as variable/constant names, but it is possible if you surround the name with back ticks `\``.



# Collection Types

Collection types used in Swift are:

- *Array*:
- *Set*:
- *Dictionary*:








Can you add ints and floats?
If you do, is the resulting variable an int (narrowing conversion) or a float (widening conversion)? Can you put different data types in the same array or list? Can one data type be converted to another (int to float, string to int, etc)?


1. What are the naming requirements for variables in your language? What about naming conventions? Are they enforced by the compiler/interpreter, or are they just standards in the community?
2. Is your language statically or dynamically typed?
3. Strongly typed or weakly typed?
4. If you put this line (or something similar) in a program and try to print x, what does it do? If it
doesn't compile, why? Is there something you can do to make it compile?
x = "5" + 6
5. Describe the limitations (or lack thereof) of your programming language as they relate to the coding portion of the assignment (adding ints and floats, storing different types in lists, etc). Are there other restrictions or pitfalls that the documentation mentions that you need to be aware of?
6. How do type conversions work in your language? Are the conversions narrowing or widening, and do they work by default or do they have to be declared by the programmer?






# Sources

iOS Developer Library https://developer.apple.com/library/ios/documentation/Swift/Conceptual/Swift_Programming_Language/TheBasics.html#//apple_ref/doc/uid/TP40014097-CH5-ID309 Accessed 10 Feb. 2016
