# Learn Swift

## Table of contents

   1. [Beginner](#level-beginners)
      1. [Module 1: Introduction to Swift](#module-1-introduction-to-swift)
         1. [Swift Basics](#swift-basics)
         2. [Comments in Swift](#comments-in-swift)
      2. [Module 2: Basic concepts in Swift](#module-2-basic-concepts-in-swift)
         1. [Introduction](#introduction)
         2. [Type Annotations](#type-annotations)
         3. [Integers and Floating-Points](#integers-and-floating-points)
         4. [Strings and Characters](#strings-and-characters)
         5. [Booleans](#booleans)
         6. [Operators](#operators)
         7. [Enumerations](#enumerations)
      3. [Module 3: Control Flows](#module-3-control-flows)
         1. [Conditionals](#conditionals)
         2. [Loops](#loops)
         3. [Control Transfers](#control-transfers)
      4. [Module 4: Functions](#module-4-functions)
         1. [Introduction](#introduction)
         2. [Specify Argument and Parameters](#specify-argument-and-parameters)
         3. [Function Types](#function-types)
   2. [Intermediate](#level-intermediate)
      1. [Module 5: Optionals](#module-5-optionals)
         1. [Theory](#theory)
         2. [Binding](#binding)
         3. [Chaining](#chaining)
         4. [Nil-Coalescing Operator](#nil-coalescing-operator)
         5. [Unconditional Unwrapping](#unconditional-unwrapping)
      2. [Module 6: Collection Types](#module-6-collection-types)
         1. [Start](#start)
         2. [Arrays](#arrays)
         3. [Sets](#sets)
         4. [Dictionaries](#dictionaries)
      3. [Module 7: Object oriented programming](#module-7-object-oriented-programming)
         1. [Classes and Structure](#classes-and-structure)
         2. [Declaration](#declaration)
         3. [Inheritance](#inheritance)
         4. [Protocols](#protocols)
         5. [Extensions](#extensions)
      4. [Module 8: Error Handling](#module-8-error-handling)
         1. [Start](#start)
         2. [Representing / Throwing Errors](#representing-throwing-errors)
         3. [Handling Errors](#handling-errors)
   3. [Advanced](#level-advanced)
      1. [Module 9: Functional Programming](#module-9-functional-programming)
         1. [Closures](#closures)
         2. [Generics](#generics)
      2. [Module 10: Advanced Swift-Lectures](#module-10-advanced-swift-lectures)
         1. [Property Observers](#property-observers)
         2. [Type Casting](#type-casting)


### Level Beginners

#### Module 1: Introduction to Swift

##### Swift Basics
A variable can be created using the keyword `var`. Constants can be created using `let`. To print the value out, use the function `print()`.

Unlike other languages like C or C++, you don't need to specify the data type. The compiler recognizes the data types automatically. In the next module, you will learn about different data types.

```swift
var variable1 = 0
let constant = 1

print(variable1)
print(constant)

variable1 = 5
print(variable1)

// Compiler-Error
// constant = 10
```

[Swift Documentation: The Basics](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html)

##### Comments in Swift
Use comments to include nonexecutable text in your code, as a note or reminder to yourself. Comments are ignored by the Swift compiler when your code is compiled.

Comments in Swift are very similar to comments in C. Single-line comments begin with two forward-slashes (`//`).

Multiline comments start with a forward-slash followed by an asterisk (`/*`) and end with an asterisk followed by a forward-slash (`*/`):

```swift
// This is a comment

/* This is also a comment
but is written over multiple lines. */
```

[Swift Documentation: Comments](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html#ID315)

#### Module 2: Basic concepts in Swift

##### Introduction
Constants and variables must be declared before they’re used. You declare constants with the `let` keyword and variables with the `var` keyword.

Here’s an example of how constants and variables can be used to track the number of login attempts a user has made. The result will get with `print` printed out. Use String Interpolation (`\( )`) to print out the variable in a `String`.

```swift
let maximumNumberOfLoginAttempts = 10
var currentLoginAttempt = 0

print("The maximum number of login attempts is \(maximumNumberOfLoginAttempts)")
print("The current number of login attempts is \(currentLoginAttempt)")
```

[Swift Documentation: Declaring Constants and Variables](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/thebasics#Declaring-Constants-and-Variables)

##### Type Annotations
You can provide a `type annotation` when you declare a constant or variable, to be clear about the kind of values the constant or variable can store. 
Write a type annotation by placing a colon after the constant or variable name, followed by a space, followed by the name of the type to use.

This example provides a type annotation for a variable called `welcomeMessage`, to indicate that the variable can store String values:

```swift
var welcomeMessage: String

// The welcomeMessage variable can now be set to any string value without error:
welcomeMessage = "Hello"
print(welcomeMessage)
```

[Swift Documentation: Type Annotations](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/thebasics/#Type-Annotations)

##### Integers and Floating-Points
*Integers* are whole numbers with no fractional component, such as 42 and -23. Integers are either signed (positive, zero, or negative) or unsigned (positive or zero).

*Floating-point* numbers are numbers with a fractional component, such as 3.14159, 0.1, and -273.15. Floating-point types can represent a much wider range of values than integer types, and can store numbers that are much larger or smaller than can be stored in an Int. Swift provides two signed floating-point number types:

- Double represents a 64-bit floating-point number.
- Float represents a 32-bit floating-point number.

Double has a precision of at least 15 decimal digits, whereas the precision of `Float` can be as little as 6 decimal digits. The appropriate
floating-point type to use depends on the nature and range of values you need to work with in your code.

In situations where either type would be appropriate, `Double` is preferred.

```swift
let age = 12 // int
let note = 1.7 // double
print(age)
print(note)
```

[Swift Documentation: Int](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/thebasics#Int)

##### Strings and Characters
A *string* is a series of characters, such as "hello, world" or "albatross". Swift strings are represented by the `String` type. The contents of a `String` can be accessed in various ways, including as a collection of `Character` values.

You can include predefined `String` values within your code as string literals. A string literal is a sequence of characters surrounded by double quotation marks ("").

Use a string literal as an initial value for a constant or variable:

```swift
let someString = "Some string literal value"
print(someString)
```

[Swift Documentation: String Literals](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/stringsandcharacters#String-Literals)

##### Booleans
Swift has a basic Boolean type, called `Bool`. Boolean values are referred to as logical, because they can only ever be `true` or `false`.

```swift
let orangesAreOrange = true
let turnipsAreDelicious = false
print(orangesAreOrange)
print(turnipsAreDelicious)
```

[Swift Documentation: Booleans](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/thebasics#Booleans)

##### Operators
Operators are unary, binary, or ternary:

- Unary operators operate on a single target (such as `-a`). Unary prefix operators appear immediately before their target (such as `!b`), and unary postfix operators appear immediately after their target (such as `c!`).
- Binary operators operate on two targets (such as `2 +

 3`) and are infix because they appear in between their two targets.
- Ternary operators operate on three targets. Like C, Swift has only one ternary operator, the ternary conditional operator (`a ? b : c`).

The values that operators affect are operands. In the expression `1 + 2`, the + symbol is an infix operator and its two operands are the values 1 and 2.

```swift
// Unary Operators: -a
// Binary Operators: 2 + 3
// Ternary Operators: a ? b : c
```

[Swift Documentation: Terminology](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/basicoperators#Terminology)

##### Enumerations
*Enumerations* (or `enums`) in Swift are a powerful feature that allows you to define a common type for a group of related values and work with those values in a type-safe way. Swift enumerations are more flexible than their counterparts in many other languages. They can have associated values and methods.

```swift
enum CompassPoint {
    case north
    case south
    case east
    case west
}

// or
enum CompassPointVariant2 {
    case north, south, east, west
}
```

[Swift Documentation: Enumeration Syntax](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/enumerations#Enumeration-Syntax)

#### Module 3: Control Flows

##### Conditionals
It’s often useful to execute different pieces of code based on certain conditions. You might want to run an extra piece of code when an error occurs, or to display a message when a value becomes too high or too low. To do this, you make parts of your code conditional.

Swift provides two ways to add conditional branches to your code: the `if` statement and the `switch` statement. Typically, you use the if statement to evaluate simple conditions with only a few possible outcomes. The switch statement is better suited to more complex conditions with multiple possible permutations and is useful in situations where pattern matching can help select an appropriate code branch to execute.

```swift
if <statement> {
    // do something
}

switch <some value> {
    case <Nr. 1>:
        // do something
    case <Nr. 2>:
        // do something
    default:
        // do something
}
```

[Swift Documentation: Control Flow](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/controlflow)

##### Loops
You use the `for-in` loop to iterate over a sequence, such as items in an array, ranges of numbers, or characters in a string.

Here are some examples:

```swift
// Iterate over the items in an array
let names = ["Anna", "Alex", "Brian", "Jack"]
for name in names {
    print("Hello, \(name)!")
}

// Iterate over a range of numbers from 1 to 5
for index in 1...5 {
    print("\(index)! times 5 is \(index * 5)!")
}

// the half-open range operator (..<) includes the
// lower bound but not the upper bound.
// 1..<6 is equal to 1...5

// If you don’t need each value from a sequence,
// you can ignore the values by using an underscore
// in place of a variable name.
for _ in 1...5 {
    print("Loops are cool")
}
```

[Swift Documentation: For-In Loops](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/controlflow#For-In-Loops)

##### Control Transfers
*Control transfer statements* change the order in which your code is executed, by transferring control from one piece of code to another. Swift has five control transfer statements:

- `continue`
- `break`
- `fallthrough`
- `return`
- `throw`

The `continue`, `break`, and `fallthrough` statements are described below. The `return` statement is described in **Module: Functions**, and the `throw` statement is described in **Module: Error Handling**.

```swift
for number in 1...10 {
    if number % 2 == 0 {
        continue
    }
    print(number)
}

for number in 1...10 {
    if number == 5 {
        break
    }
    print(number)
}

let number = 3

switch number {
case 1:
    print("The number is 1")
case 2:
    print("The number is 2")
case 3:
    print("The number is 3")
    fallthrough // Continue to the next case
case 4:
    print("The number is 4")
    fallthrough // Continue to the next case
case 5:
    print("The number is 5")
default:
    print("The number is something else")
}
```

[Swift Documentation: Control Transfer Statements](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/controlflow#Control-Transfer-Statements)

#### Module 4: Functions

##### Introduction
When defining a *function*, you can optionally define named, typed input values called `parameters`, and a type for the output value, known as the `return` type. Every function has a name describing its task. To use a function, you "call" it with its name and provide input values, or arguments, matching the function’s parameters in the specified order.

To demonstrate this, there are two functions:

- The function `greet(person:)`, takes a person’s name as input and returns a greeting. It defines one input parameter—a String called person—and a return type of String for the greeting.
- The function `helloWorld()` takes no parameters and returns nothing; it only prints "Hello World".

```swift
func greet(person: String) -> String {
    let greeting = "Hello, " + person + "!"
    return greeting
}

func helloWorld() {
    print("Hello World")
}

print(greet(person: "Anna"))
print(greet(person: "Brian"))

helloWorld()
```

[Swift Documentation: Defining and Calling Functions](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/functions#Defining-and-Calling-Functions)

##### Specify Argument and Parameters
Each function parameter has both an *argument label* and a *parameter name*. The argument label is used when calling the function; each argument is written in the function call with its argument label before it. The parameter name is used in the implementation of the function. By default, parameters use their parameter name as their argument label.

You can specify an argument label before the parameter name, separated by a space.
Here’s a variation of the `greet(person:)` function that takes a person’s name and hometown and returns a greeting:

```swift
func greet(person: String, from hometown: String) -> String {
    return "Hello \(person)!  Glad you could visit from \(hometown)."
}

print(greet(person: "Bill", from: "Cupertino"))
```

[Swift Documentation: Function Argument Labels and Parameter Names](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/functions#Function-Argument-Labels-and-Parameter-Names)

##### Function Types
Every function has a specific *function type*, made up of the parameter types and the return type of the function.

For example:

```swift
func addTwoInts(_ a: Int, _ b: Int) -> Int {
    return a + b
}

func multiplyTwoInts(_ a: Int, _ b: Int) -> Int {
    return a * b
}

func printHelloWorld() {
    print("hello, world")
}
```

The type of both of these functions is:

```swift
(Int, Int) -> Int
```

This can be read as: “A function that has two parameters, both of type Int, and that returns a value of type Int.”

Here’s another example, for a function with no parameters or return value:

```swift
func printHelloWorld() { print("hello, world") }
```

The type of this function is `() -> Void`, or “a function that has no parameters, and returns Void.”

[Swift Documentation: Function Types](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/functions#Function-Types)

### Level Intermediate

#### Module 5: Optionals

##### Theory
Optionals are a fundamental feature in Swift. They allow you to declare variables or constants that can either hold a value or be `nil` (no value).

Swift’s type system usually shows the wrapped type’s name with a trailing question mark (?) instead of showing the full type name. For example, if a variable has the type `Int?`, that’s just another way of writing `Optional<Int>`.

```swift
var ageShort: Int?
var ageLong: Optional<Int>
```

[Apple Documentation: Optional](https://developer.apple.com/documentation/swift/optional#overview)

##### Binding
To conditionally bind the wrapped value of an Optional instance to a new variable, use one of the optional binding control structures, including `if let`, `guard let`, and `switch`.

Here are some examples:

```swift
var age: Int? = nil

if let unwrappedAge = age {
    print(unwrappedAge)
} else {
    print("Age is nil")
}

var name: String? = "Max"
guard let unwrappedName = name else { 
    print("Name is nil")
    return
}

print(unwrappedName)
```

[Apple Documentation: Optional Binding](https://developer.apple.com/documentation/swift/optional#Optional-Binding)

##### Chaining
To safely access the properties and methods of a wrapped instance, use the postfix optional chaining

 operator (postfix `?`).

Here is an example
(You will learn classes in the **Module 7: Object Oriented Programming**):

```swift
class Person {
    var residence: Residence?
}

class Residence {
    var numberOfRooms = 1
}

let john = Person()
if let roomCount = john.residence?.numberOfRooms {
    print("John's residence has \(roomCount) room(s).")
} else {
    print("Unable to retrieve the number of rooms.")
}
```

[Apple Documentation: Optional Chaining](https://developer.apple.com/documentation/swift/optional#Optional-Chaining)

##### Nil-Coalescing Operator
Use the nil-coalescing operator (??) to supply a default value in case the `Optional` instance is `nil`.

Here is a simple example:

```swift
var optionalCar: String? = "BMW"
print(optionalCar ?? "There is no car")
```

[Apple Documentation: Nil-Coalescing Operator](https://developer.apple.com/documentation/swift/optional#Using-the-Nil-Coalescing-Operator)

##### Unconditional Unwrapping
When you’re certain that an instance of Optional contains a value, you can unconditionally unwrap the value by using the forced unwrap operator (postfix !).
Note: Unconditionally unwrapping a nil instance with `!` triggers a runtime error.

Here is a simple example:

```swift
var optionalCar: String? = "BMW"
print(optionalCar!)

// This code will
// crash the App
// var crashVariable: String? = nil
// print(crashVariable!)
```

[Apple Documentation: Unconditional Unwrapping](https://developer.apple.com/documentation/swift/optional#Unconditional-Unwrapping)

#### Module 6: Collection Types

##### Start
Swift provides three primary *collection types*, known as arrays, sets, and dictionaries, for storing collections of values.
Arrays are ordered collections of values. Sets are unordered collections of unique values. Dictionaries are unordered collections of key-value associations.

Arrays, sets, and dictionaries in Swift are always clear about the types of values and keys that they can store. This means that you can’t insert a value of the wrong type into a collection by mistake. It also means you can be confident about the type of values you will retrieve from a collection.

[Swift Documentation: Collection Types](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/collectiontypes)

##### Arrays
An *array* stores values of the same type in an ordered list. The same value can appear in an array multiple times at different positions.

You can create an empty array of a certain type using initializer syntax.
Swift’s Array type also provides an initializer for creating an array of a certain size with all of its values set to the same default value. You pass this initializer a default value of the appropriate type (called `repeating`): and the number of times that value is repeated in the new array (called `count`):

```swift
var arrayOfInts: [Int] = []
var arrayOfDoubles: [Double] = Array(repeating: 0.0, count: 3)

print(arrayOfInts)
print(arrayOfDoubles)
```

[Swift Documentation: Arrays](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/collectiontypes#Arrays)

You access and modify an array through its methods and properties, or by using subscript syntax.

Here are some examples:

```swift
var shoppingList = ["Eggs", "Toast", "Cornflakes"]
print("The shopping list contains \(shoppingList.count) items.")

if shoppingList.isEmpty {
    print("The shopping list is empty.")
} else {
    print("The shopping list isn't empty.")
}

// Add
shoppingList.append("Flour")
shoppingList += ["Baking Powder"]
print("The shopping list contains \(shoppingList)")

// Access
print("The first item of the shopping list is: \(shoppingList[0])")

// Modify
shoppingList[0] = "Six eggs"
print("The first item of the shopping list is: \(shoppingList[0])")

// Remove
let cornflakes = shoppingList.remove(at: 2)
let bakingPowder = shoppingList.removeLast()
```

[Swift Documentation: Accessing and Modifying an Array](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/collectiontypes#Accessing-and-Modifying-an-Array)

You can iterate over the entire set of values in an array with the `for-in` loop:

```swift
var shoppingList = ["Eggs", "Toast", "Cornflakes"]

for item in shoppingList {
    print(item)
}
```

[Swift Documentation: Iterating Over an Array](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/collectiontypes#Iterating-Over-an-Array)

##### Sets
A *set* stores distinct values of the same type in a collection with no defined ordering. You can use a set instead of an array when the order of items isn’t important, or when you need to ensure that an item only appears once.

You can create an empty set of a certain type using initializer syntax:

```swift
var letters = Set<Character>()
print("letters is of type Set<Character> with \(letters.count) items.")

// Initialize a set with an array literal
var favoriteGenres: Set<String> = ["Rock", "Classical", "Hip hop"]
print(favoriteGenres)
```

[Swift Documentation: Sets](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/collectiontypes#Sets)

You access and modify a `set` through its methods and properties.

Here are some examples:

```swift
var favoriteGenres: Set<String> = ["Rock", "Classical", "Hip hop"]

if favoriteGenres.isEmpty {
    print("As far as music goes, I'm not picky.")
} else {
    print("I have particular music preferences.")
}

favoriteGenres.insert("Jazz")
print(favoriteGenres)

if let removedGenre = favoriteGenres.remove("Rock") {
    print("\(removedGenre)? I'm over it.")
} else {
    print("I never much cared for that.")
}

if favoriteGenres.contains("Funk") {
    print("I get up on the good foot.")
} else {
    print("It's too funky in here.")
}
```

[Swift Documentation: Accessing and Modifying a Set](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/collectiontypes#Accessing-and-Modifying-a-Set)

You can iterate over the values in a set with a `for-in` loop.

```swift
var favoriteGenres: Set<String> = ["Rock", "Classical", "Hip hop"]

for genre in favoriteGenres {
    print("\(genre)")
}
```

[Swift Documentation: Iterating Over a Set](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/collectiontypes#Iterating-Over-a-Set)

You can efficiently perform fundamental set operations, such as combining two sets together, determining which values two sets have in common, or determining whether two sets contain all, some, or none of the same values.

- Use the `intersection(_:)` method to create a new set with only the values common to both sets.
- Use the `symmetricDifference(_:)` method to create a new set with values in either set, but not both.
- Use the `union(_:)` method to create a new set with all of the values in both sets.
- Use the `subtracting(_:)` method to create a new set with values not in the specified set.

Here's an example:

```swift
let oddDigits: Set = [1, 3, 5, 7, 9]
let evenDigits: Set = [0, 2, 4, 6, 8]
let singleDigitPrimeNumbers: Set = [2, 3, 5, 7]

let unionDigits = oddDigits
.union(evenDigits)
.sorted()
print(unionDigits)

let intersectionDigits = oddDigits
.intersection(evenDigits)
.sorted()
print(intersectionDigits)

let subtractingDigits = oddDigits
.subtracting(singleDigitPrimeNumbers)
.sorted()
print(subtractingDigits)

let symmetricDifferenceDigits = oddDigits
.symmetricDifference(singleDigitPrimeNumbers)
.sorted()
print(symmetricDifferenceDigits)
```

[Swift Documentation: Performing Set Operations](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/collectiontypes#Performing-Set-Operations)

##### Dictionaries
A *dictionary* stores associations between keys of the same type and values of the same type in a collection with no defined ordering. Each value is associated with a *unique key*, which acts as an identifier for that value within the dictionary. Unlike items in an array, items in a dictionary don’t have a specified order. You use a dictionary when you need to look up values based on their identifier, in much the same way that a real-world dictionary is used to look up the definition for a particular word.

As with arrays, you can create an empty Dictionary of a certain type by using initializer syntax:

```swift
var namesOfIntegers: [Int: String] = [:]
```

[Swift Documentation: Dictionaries](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/collectiontypes#Dictionaries)

You access and modify a dictionary through its methods and properties, or by using subscript syntax.

Here are some examples:

```swift
var airports = ["YYZ": "Toronto Pearson", "DUB": "Dublin"]
print("The airports dictionary contains \(airports.count) items.")

if airports.isEmpty {
    print("The airports dictionary is empty.")
} else {
    print("The airports dictionary isn't empty.")
}

//

 Add
airports["LHR"] = "London"

// Update
if let oldValue = airports.updateValue("Dublin Airport", forKey: "DUB") {
    print("The old value for DUB was \(oldValue).")
}

// Access
if let airportName = airports["DUB"] {
    print("The name of the airport is \(airportName).")
} else {
    print("That airport isn't in the airports dictionary.")
}

// Remove
airports["APL"] = "Apple International"
// "Apple International" isn't the real airport for APL, so delete it
airports["APL"] = nil

if let removedValue = airports.removeValue(forKey: "DUB") {
    print("The removed airport's name is \(removedValue).")
} else {
    print("The airports dictionary doesn't contain a value for DUB.")
}
```

[Swift Documentation: Accessing and Modifying a Dictionary](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/collectiontypes#Accessing-and-Modifying-a-Dictionary)

You can iterate over the key-value pairs in a dictionary with a `for-in` loop. Each item in the dictionary is returned as a `(key, value)` tuple, and you can decompose the tuple’s members into temporary constants or variables as part of the iteration:

```swift
var airports = ["YYZ": "Toronto Pearson", "DUB": "Dublin"]

for (airportCode, airportName) in airports {
    print("\(airportCode): \(airportName)")
}
```

[Swift Documentation: Iterating Over a Dictionary](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/collectiontypes#Iterating-Over-a-Dictionary)

#### Module 7: Object oriented programming

##### Classes and Structure
In Swift, classes and structures are versatile and flexible constructs that can be used to build your program’s code. Both classes and structures can:

- Define properties to store values.
- Define methods to provide functionality.
- Define subscripts to provide access to their values using subscript syntax.
- Define initializers to set up their initial state.
- Be extended to expand their functionality beyond a default implementation.
- Conform to protocols to provide standard functionality of a certain kind.

[Swift Documentation: Classes and Structures](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/classesandstructures)

There are also significant differences between classes and structures in Swift:

Classes:
1. Inheritance: Classes can inherit from other classes. This means a class can gain the characteristics of another class.
2. Type Casting: You can check and interpret the type of a class instance at runtime.
3. Deinitializers: Classes can define deinitializers, which allow an instance of a class to free up any resources it has assigned.
4. Reference Counting: Classes are reference types and are managed by automatic reference counting (ARC).

Structures:
1. No Inheritance: Structures do not support inheritance. They cannot inherit from other structures.
2. Value Types: Structures are value types. When you assign or pass around a structure, you are making a copy of it.
3. Mutability: To modify a property of a structure, you must mark it as mutating if it changes any properties of the structure within its methods.

[Swift Documentation: Comparing Structures and Classes](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/classesandstructures#Comparing-Structures-and-Classes)

##### Declaration
Both classes and structures are declared using the class and struct keywords, respectively. Both can have properties and methods defined within them.

Here’s an example:

```swift
struct Resolution {
    var width = 0
    var height = 0
}

class VideoMode {
    var resolution = Resolution()
    var interlaced = false
    var frameRate = 0.0
    var name: String?
}

// create instances of structures and classes using initializer syntax:
let someResolution = Resolution()
let someVideoMode = VideoMode()
```

[Swift Documentation: Definition Syntax](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/classesandstructures#Definition-Syntax)

When you assign an instance of a structure to a new variable or constant, or when you pass it to a function, the instance is copied.

```swift
struct Resolution {
    var width = 0
    var height = 0
}

let hd = Resolution(width: 1920, height: 1080)
var cinema = hd

cinema.width = 2048
print(hd.width)
```

[Swift Documentation: Structures and Enumerations Are Value Types](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/classesandstructures#Structures-and-Enumerations-Are-Value-Types)

When you assign an instance of a class to a new variable or constant, or when you pass it to a function, you are referencing the same instance.

```swift
struct Resolution {
    var width = 0
    var height = 0
}

class VideoMode {
    var resolution = Resolution()
    var interlaced = false
    var frameRate = 0.0
    var name: String?
}

let hd = Resolution(width: 1920, height: 1080)
let tenEighty = VideoMode()
tenEighty.resolution = hd
tenEighty.interlaced = true
tenEighty.name = "1080i"
tenEighty.frameRate = 25.0

let alsoTenEighty = tenEighty
alsoTenEighty.frameRate = 30.0
print(tenEighty.frameRate)
```

[Swift Documentation: Structures and Enumerations Are Value Types](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/classesandstructures#Structures-and-Enumerations-Are-Value-Types)

Since classes are reference types, it is possible to check if two constants or variables refer to the same instance of a class using the identity operators (`===` and `!==`).

```swift
struct Resolution {
    var width = 0
    var height = 0
}

class VideoMode {
    var resolution = Resolution()
    var interlaced = false
    var frameRate = 0.0
    var name: String?
}

let hd = Resolution(width: 1920, height: 1080)
let tenEighty = VideoMode()
tenEighty.resolution = hd
tenEighty.interlaced = true
tenEighty.name = "1080i"
tenEighty.frameRate = 25.0

let alsoTenEighty = tenEighty
alsoTenEighty.frameRate = 30.0

if tenEighty === alsoTenEighty {
    print("tenEighty and alsoTenEighty refer to the same VideoMode instance.")
}
```

[Swift Documentation: Identity Operators](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/classesandstructures#Identity-Operators)

##### Inheritance
*Inheritance* is a mechanism in which one class (called a subclass) inherits the properties and methods of another class (called a superclass). In Swift, inheritance allows you to create a new class based on an existing class, thereby reusing code and adding new features to the existing class.

[Swift Documentation: Inheritance](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/inheritance/)

A base class is any class that doesn’t inherit from another class.

*Subclassing* is the act of basing a new class on an existing class. The subclass inherits characteristics from the existing class, which you can then refine. You can also add new characteristics to the subclass. To create a subclass, you specify the subclass's name before the superclass's name, separated by a colon.

The example below defines a base class called *Vehicle*. This base class defines a stored property called `currentSpeed`, with a default value of `0.0` (inferring a property type of `Double`). The `currentSpeed` property’s value is used by a read-only computed `String` property calle`description` to create a description of the vehicle. The `Vehicle` base class also defines a method called `makeNoise`. This method doesn’t actually do anything for a base `Vehicle` instance.

`Bicycle` is a subclass of `Vehicle`. It inherits all properties and methods from `Vehicle`, and also introduces a new property `hasBasket`.

```swift
class Vehicle {
    var currentSpeed = 0.0
    var description: String {
        return "traveling at \(currentSpeed) miles per hour"
    }
    func makeNoise() {
        // do nothing - an arbitrary vehicle doesn't necessarily make a noise
    }
}

class Bicycle: Vehicle {
    var hasBasket = false
}

let bicycle = Bicycle()
print(bicycle.description)
```

[Swift Documentation: Defining a Base Class](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/inheritance#Defining-a-Base-Class)

You can override an inherited instance or type method to provide a tailored or alternative implementation of the method within your subclass.

The following example defines a new subclass of `Vehicle` called `Train`, which overrides the `makeNoise()` method that `Train` inherits from `Vehicle`:

```swift
class Vehicle {
    var currentSpeed = 0.0
    var description: String {
        return "traveling at \(currentSpeed) miles per hour"
    }
    func makeNoise() {
        // do nothing - an arbitrary vehicle doesn't necessarily make a noise
    }
}

class Train: Vehicle {
    override func makeNoise() {
        print("Choo Choo")
    }
}

let train = Train()
print(train.makeNoise())
```

[Swift Documentation: Overriding Methods](https://docs.swift

.org/swift-book/documentation/the-swift-programming-language/inheritance#Overriding-Methods)

You can also override properties, including computed properties, to modify their behavior or provide custom getters and setters.

Here, the `Car` class overrides the `description` property of its superclass `Vehicle` to add information about the car’s gear.

```swift
class Vehicle {
    var currentSpeed = 0.0
    var description: String {
        return "traveling at \(currentSpeed) miles per hour"
    }
    func makeNoise() {
        // do nothing - an arbitrary vehicle doesn't necessarily make a noise
    }
}

class Car: Vehicle {
    var gear = 1
    override var description: String {
        return super.description + " in gear \(gear)"
    }
}

let car = Car()
print(car.description)
```

[Swift Documentation: Overriding Properties](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/inheritance#Overriding-Properties)

You can prevent a method, property, or subscript from being overridden by marking it as `final`. Do this by writing the `final` modifier before the method, property, or subscript’s introducer keyword (such as `final var`, `final func`, `final class func`, and `final subscript`).

If you try to subclass `Train` or override its methods or properties, Swift will generate a compile-time error.

```swift
final class Train: Vehicle {
    override func makeNoise() {
        print("Choo Choo")
    }
}
```

[Swift Documentation: Preventing Overrides](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/inheritance#Preventing-Overrides)

##### Protocols
A *protocol* defines a blueprint of methods, properties, and other requirements that suit a particular task or piece of functionality. Classes, structures, and enumerations can adopt protocols and provide implementations for the requirements defined in those protocols.

[Swift Documentation: Protocols](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/protocols)

In this example, `SomeProtocol` defines an instance property requirement (`mustBeSettable` and `doesNotNeedToBeSettable`), a type property requirement (`someTypeProperty`), an instance method requirement (`someMethod`), a mutating instance method requirement (`changeSomething`), and a type method requirement (`someTypeMethod`).

```swift
protocol SomeProtocol {
    var mustBeSettable: Int { get set }
    var doesNotNeedToBeSettable: Int { get }
    static var someTypeProperty: Int { get set }

    func someMethod()
    mutating func changeSomething()
    static func someTypeMethod()
}
```

[Swift Documentation: Defining Protocols](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/protocols)

A `protocol` can require any conforming type to provide an instance property or instance method with a particular name and type. The protocol does not specify whether the property should be a stored property or a computed property. It only specifies the required property name and type.

```swift
protocol FullyNamed {
    var fullName: String { get }
}

struct Person: FullyNamed {
    var fullName: String
}

let john = Person(fullName: "John Appleseed")
print(john.fullName)
```

[Swift Documentation: Property Requirements](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/protocols#Property-Requirements)

A `protocol` can inherit one or more other protocols and can add further requirements on top of the requirements it inherits.

```swift
protocol InheritingProtocol: SomeProtocol, AnotherProtocol {
    // additional requirements go here
}
```

[Swift Documentation: Protocol Inheritance](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/protocols#Protocol-Inheritance)

You can combine multiple protocols into a single requirement using a `protocol` composition.

```swift
protocol Named {
    var name: String { get }
}

protocol Aged {
    var age: Int { get }
}

struct Person: Named, Aged {
    var name: String
    var age: Int
}

func wishHappyBirthday(to celebrator: Named & Aged) {
    print("Happy birthday, \(celebrator.name), you're \(celebrator.age)!")
}

let birthdayPerson = Person(name: "John", age: 21)
wishHappyBirthday(to: birthdayPerson)
```

[Swift Documentation: Protocol Composition](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/protocols#Protocol-Composition)

##### Extensions
*Extensions* add new functionality to an existing class, structure, enumeration, or protocol type. This includes the ability to extend types for which you do not have access to the original source code (known as retroactive modeling).

[Swift Documentation: Extensions](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/extensions)

Declare extensions with the `extension` keyword:

Extensions can add computed instance properties, computed type properties, and new methods to existing types.

```swift
extension Double {
    var km: Double { return self * 1_000.0 }
    var m: Double { return self }
    var cm: Double { return self / 100.0 }
    var mm: Double { return self / 1_000.0 }
    var ft: Double { return self / 3.28084 }

    func printCurrentValue() {
        print("The current value is \(self)")
    }
}

let number = 25.4
print("One inch is \(number.mm) meters")
number.printCurrentValue()
```

[Swift Documentation: Extension Syntax](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/extensions#Extension-Syntax)

Instance methods added with an extension can also modify (or *mutate*) the instance itself. Structure and enumeration methods that modify `self` or its properties must mark the instance method as `mutating`, just like mutating methods from an original implementation.

The example below adds a new mutating method called square to Swift’s Int type, which squares the original value:

```swift
extension Int {
    mutating func square() {
        self = self * self
    }
}

var someInt = 3
someInt.square()
print(someInt)
```

[Swift Documentation: Mutating Instance Methods](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/extensions#Mutating-Instance-Methods)

#### Module 8: Error Handling

##### Start
*Error handling* is the process of responding to and recovering from error conditions in your program. Swift provides first-class support for throwing, catching, propagating, and manipulating recoverable errors at runtime.

Some operations aren’t guaranteed to always complete execution or produce a useful output. Optionals are used to represent the absence of a value, but when an operation fails, it’s often useful to understand what caused the failure, so that your code can respond accordingly.

As an example, consider the task of reading and processing data from a file on disk. There are a number of ways this task can fail, including the file not existing at the specified path, the file not having read permissions, or the file not being encoded in a compatible format. Distinguishing among these different situations allows a program to resolve some errors and to communicate to the user any errors it can’t resolve.

[Swift Documentation: Error Handling](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/errorhandling)

##### Representing / Throwing Errors
In Swift, errors are represented by values of types that conform to the `Error` protocol. This empty protocol indicates that a type can be used for error handling.

Swift enumerations are particularly well suited to modeling a group of related error conditions, with associated values allowing for additional information about the nature of an error to be communicated. For example, here’s how you might represent the error conditions of operating a vending machine inside a game:

```swift
enum VendingMachineError: Error {
    case invalidSelection
    case insufficientFunds(coinsNeeded: Int)
    case outOfStock
}
```

[Swift Documentation: Representing and Throwing Errors](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/errorhandling#Representing-and-Throwing-Errors)

##### Handling Errors
There are four ways to handle errors in Swift:

1. Propagating Errors Using `throws`
   A function or method that can throw an error must be marked with the `throws` keyword. When calling this function, you must handle the error using a `try` keyword.
   
2. Do-Catch
   You can handle errors using a `do-catch` block. Inside the do block, you use try to call functions that can throw errors. In the catch blocks, you handle the errors.
   
3. Optional Try?
   You can convert an error to an optional value using `try?`. If an error is thrown, the expression evaluates to `nil`.
   
4. Force Try!
   You can disable error propagation using `try!`, which will cause a runtime error if an error is thrown.

Here are some examples:

```swift
enum DivisionError: Error {
    case divisionByZero
}

// 1.
func divide(_ numerator: Double, by denominator: Double) throws -> Double {
    if denominator == 0 {
        throw DivisionError.divisionByZero
    }
    return numerator / denominator
}

// 2.
do {
    let result = try divide(10, by: 2)
    print("Result: \(result)")  // This will print: Result: 5.0
} catch DivisionError.divisionByZero {
    print("Error:

 Division by zero.")
}

// 3.
if let result = try? divide(10, by: 2) {
    print("Result: \(result)")  // This will print: Result: 5.0
} else {
    print("Error: Division by zero.")
}

// 4.
let result = try! divide(10, by: 2)
print("Result: \(result)")  // This will print: Result: 5.0
```

[Swift Documentation: Propagating Errors Using Throws](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/errorhandling#Propagating-Errors-Using-Throws)

### Level Advanced

#### Module 9: Functional Programming

##### Closures
*Closures* are self-contained blocks of functionality that can be passed around and used in your code. Closures in Swift are similar to blocks in C and Objective-C and to lambdas in other programming languages. Closures can capture and store references to any constants and variables from the context in which they are defined. This is known as closing over those constants and variables.

Here’s an example of a closure that captures values from its surrounding context:

```swift
let incrementByTwo = { (number: Int) -> Int in
    return number + 2
}

let result = incrementByTwo(3)
print(result)  // This will print: 5
```

[Swift Documentation: Closures](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/closures)

Swift provides several optimizations for closure expressions:

- Inferring Parameter and Return Types from Context
- Implicit Returns from Single-Expression Closures
- Shorthand Argument Names
- Trailing Closures

Here’s an example of a shorthand closure expression:

```swift
let names = ["Chris", "Alex", "Ewa", "Barry", "Daniella"]

let reversedNames = names.sorted(by: { $0 > $1 })
print(reversedNames)  // This will print: ["Ewa", "Daniella", "Chris", "Barry", "Alex"]
```

[Swift Documentation: Closure Expression Syntax](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/closures#Closure-Expression-Syntax)

##### Generics
*Generics* are a powerful feature of Swift that allow you to write flexible and reusable functions and types. Generic code enables you to write functions and types that can work with any type, subject to requirements that you define.

Here’s a generic function that swaps the values of two variables:

```swift
func swapTwoValues<T>(_ a: inout T, _ b: inout T) {
    let temporaryA = a
    a = b
    b = temporaryA
}

var a = 5
var b = 10
swapTwoValues(&a, &b)
print("a is now \(a), and b is now \(b)")
```

[Swift Documentation: Generics](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/generics)

#### Module 10: Advanced Swift-Lectures

##### Property Observers
*Property observers* observe and respond to changes in a property’s value. Property observers are called every time a property’s value is set, even if the new value is the same as the property’s current value. You can add property observers to any stored properties you define, except for lazy stored properties. You can also add property observers to any inherited property (whether stored or computed) by overriding the property within a subclass.

Here’s an example:

```swift
class StepCounter {
    var totalSteps: Int = 0 {
        willSet(newTotalSteps) {
            print("About to set totalSteps to \(newTotalSteps)")
        }
        didSet {
            if totalSteps > oldValue {
                print("Added \(totalSteps - oldValue) steps")
            }
        }
    }
}

let stepCounter = StepCounter()
stepCounter.totalSteps = 200
stepCounter.totalSteps = 360
stepCounter.totalSteps = 896
```

[Swift Documentation: Property Observers](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/properties#Property-Observers)

##### Type Casting
*Type casting* is a way to check the type of an instance, and/or to treat that instance as if it is a different superclass or subclass from somewhere else in its own class hierarchy.

Type casting in Swift is implemented with the `is` and `as` operators. You can use these operators to check the type of a value or cast a value to a different type.

Here’s an example:

```swift
class MediaItem {
    var name: String
    init(name: String) {
        self.name = name
    }
}

class Movie: MediaItem {
    var director: String
    init(name: String, director: String) {
        self.director = director
        super.init(name: name)
    }
}

class Song: MediaItem {
    var artist: String
    init(name: String, artist: String) {
        self.artist = artist
        super.init(name: name)
    }
}

let library = [
    Movie(name: "Casablanca", director: "Michael Curtiz"),
    Song(name: "Blue Suede Shoes", artist: "Elvis Presley"),
    Movie(name: "Citizen Kane", director: "Orson Welles"),
    Song(name: "The One And Only", artist: "Chesney Hawkes"),
    Song(name: "Never Gonna Give You Up", artist: "Rick Astley")
]

var movieCount = 0
var songCount = 0

for item in library {
    if item is Movie {
        movieCount += 1
    } else if item is Song {
        songCount += 1
    }
}

print("Media library contains \(movieCount) movies and \(songCount) songs")
```

[Swift Documentation: Type Casting](https://docs.swift.org/swift-book/documentation/the-swift-programming-language/typecasting)

