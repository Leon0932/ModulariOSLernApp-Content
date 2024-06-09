# Quizzes for Swift

## Table of contents
1. [Beginner](#level-beginners)
      1. [Module 1: Introduction to Swift](#module-1-introduction-to-swift)
         1. [Quiz 1: Create a constant](#quiz-1-create-a-constant)
         2. [Quiz 2: Learn comments](#quiz-2-learn-comments)
      2. [Module 2: Basic concepts in Swift](#module-2-basic-concepts-in-swift)
         1. [Quiz 1: Declare a variable](#quiz-1-declare-a-variable)
         2. [Quiz 2: Learn Operators](#quiz-2-learn-operators)
      3. [Module 3: Control Flows](#module-3-control-flows)
         1. [Quiz 1: Learn if-else](#quiz-1-learn-if-else)
         2. [Quiz 2: Learn switch](#quiz-2-learn-switch)
         3. [Quiz 3: Learn for-loops](#quiz-3-learn-for-loops)
         4. [Quiz 4: Learn while-loops](#quiz-4-learn-while-loops)
         5. [Quiz 5: Learn repeat-while-loops](#quiz-5-learn-repeat-while-loops)
         6. [Quiz 6: Learn continue](#quiz-6-learn-continue)
         7. [Quiz 7: Learn break](#quiz-7-learn-break)
         8. [Quiz 8: Learn fallthrough](#quiz-8-learn-fallthrough)
      4. [Module 4: Functions](#module-4-functions)
         1. [Quiz 1: Learn functions](#quiz-1-learn-functions)
         2. [Quiz 2: Learn Argument Labels I](#quiz-2-learn-argument-labels-i)
         3. [Quiz 3: Learn Argument Labels II](#quiz-3-learn-argument-labels-ii)
         4. [Quiz 4: Learn default Parameter Values](#quiz-4-learn-default-parameter-values)
         5. [Quiz 5: Learn variadic Parameters](#quiz-5-learn-variadic-parameters)
         6. [Quiz 6: Learn In-Out Parameters](#quiz-6-learn-in-out-parameters)
2. [Intermediate](#level-intermediate)
      1. [Module 5: Optionals](#module-5-optionals)
         1. [Quiz 1: Learn Bindings](#quiz-1-learn-bindings)
         2. [Quiz 2: Learn Chaining](#quiz-2-learn-chaining)
         3. [Quiz 3: Learn Nil-Coalescing](#quiz-3-learn-nil-coalescing)
         4. [Quiz 4: Learn Unconditional Unwrapping](#quiz-4-learn-unconditional-unwrapping)
      2. [Module 6: Collection Types](#module-6-collection-types)
         1. [Quiz 1: Learn Arrays](#quiz-1-learn-arrays)
         2. [Quiz 2: Learn Sets](#quiz-2-learn-sets)
         3. [Quiz 3: Learn Dictionaries](#quiz-3-learn-dictionaries)
      3. [Module 7: Object oriented programming](#module-7-object-oriented-programming)
         1. [Quiz 1: Learn Classes](#quiz-1-learn-classes)
         2. [Quiz 2: Learn Inheritance](#quiz-2-learn-inheritance)
         3. [Quiz 3: Learn Protocols](#quiz-3-learn-protocols)
         4. [Quiz 4: Learn Extensions](#quiz-4-learn-extensions)
      4. [Module 8: Error Handling](#module-8-error-handling)
         1. [Quiz 1: Learn Errors](#quiz-1-learn-errors)
3. [Advanced](#level-advanced)
      1. [Module 9: Functional Programming](#module-9-functional-programming)
         1. [Quiz 1: Learn Closures](#quiz-1-learn-closures)
         2. [Quiz 2: Learn Capturing Values](#quiz-2-learn-capturing-values)
         3. [Quiz 3: Learn Generic Functions](#quiz-3-learn-generic-functions)
      2. [Module 10: Advanced Swift-Lectures](#module-10-advanced-swift-lectures)
         1. [Quiz 1: Learn Property Observers](#quiz-1-learn-property-observers)
         2. [Quiz 2: Learn Type Casting](#quiz-2-learn-type-casting)

### Level Beginners

#### Module 1: Introduction to Swift

##### Quiz 1: Create a constant

**Description**: Create a constant named `pi` and set it to the value 3.14159. Print the variable.

**Starting Code**: ...

**Solution Code**:
```swift
let pi = 3.14159
print(pi)
```

##### Quiz 2: Learn comments

**Description**: Comment out the following line in Swift: `var x = 10`.

**Starting Code**:
```swift
var x = 10
```

**Solution Code**:
```swift
// var x = 10
```

#### Module 2: Basic concepts in Swift

##### Quiz 1: Declare a variable

**Description**:
1) Declare a variable `name` of type `String` and assign it the value "John"
2) Create a constant `age` of `Int` and set it to 18.
3) Use String Interpolation to print the following text:
"Hello, my name is John and I am 18 years old"

**Starting Code**: ...

**Solution Code**:
```swift
var name: String = "John"
let age: Int = 18
print("Hello, my name is \\(name) and I am \\(age) years old")
```

##### Quiz 2: Learn Operators

**Description**:
1) Create two constants `a` and `b` of type `Int` with the values 10 and 18.
2) Add these two variables and store the result in a new constant `sum` of type `Int`.
3) Then create a new constant of type `Int` with the name `moduleOperation` and perform *sum module 10*. Print the result.

**Starting Code**: ...

**Solution Code**:
```swift
let a: Int = 10
let b: Int = 18
let sum: Int = a + b
let moduleOperation: Int = sum % 10
print(moduleOperation)
```

### Level Intermediate

#### Module 3: Control Flows

##### Quiz 1: Learn if-else

**Description**: Write an if-else condition that checks if a number `number` is greater than 10 and prints "Greater than 10" or "Less than or equal to 10" accordingly.

**Starting Code**:
```swift
let number = 12
```

**Solution Code**:
```swift
let number = 12
if number > 10 {
    print("Greater than 10")
} else {
    print("Less than or equal to 10")
}
```

##### Quiz 2: Learn switch

**Description**: Write a switch statement that checks the value of a variable `grade` and prints "Excellent" for A, "Good" for B, "Fair" for C, "Poor" for D, "Fail" for F and for default "Invalid grade".

**Starting Code**:
```swift
let grade = "B"
```

**Solution Code**:
```swift
let grade = "B"
switch grade {
case "A":
    print("Excellent")
case "B":
    print("Good")
case "C":
    print("Fair")
case "D":
    print("Poor")
case "F":
    print("Fail")
default:
    print("Invalid grade")
}
```

##### Quiz 3: Learn for-loops


**Description**: Write a for-in loop that iterates over an array of `numbers` and prints each number.

**Starting Code**:
```swift
let numbers = [1, 2, 3, 4, 5]
```

**Solution Code**:
```swift
let numbers = [1, 2, 3, 4, 5]
for number in numbers {
    print(number)
}
```

##### Quiz 4: Learn while-loops

**Description**: Write a

 while loop that counts down from 5 to 1 and prints each number (use the `-=` operator).

**Starting Code**:
```swift
var counter = 5
```

**Solution Code**:
```swift
var counter = 5
while counter > 0 {
    print(counter)
    counter -= 1
}
```

##### Quiz 5: Learn repeat-while-loops

**Description**: Write a `repeat-while` loop that counts up from 1 to 5 and prints each number (use the `+=` operator).

**Starting Code**:
```swift
var count = 1
```

**Solution Code**:
```swift
var count = 1
repeat {
    print(count)
    count += 1
} while count <= 5
```

##### Quiz 6: Learn continue

**Description**: Write a for-in loop that iterates over the numbers from 1 to 10 and only prints the even numbers.

**Starting Code**:
```swift
for number in 1...10 {
    ...
}
```

**Solution Code**:
```swift
for number in 1...10 {
    if number % 2 == 0 {
        print(number)
    }
    continue
}
```

##### Quiz 7: Learn break

**Description**: Write a for-in loop that iterates over the numbers from 1 to 10 and breaks the loop when it reaches an even number.

**Starting Code**:
```swift
for i in 1...10 {
    ...
}
```

**Solution Code**:
```swift
for i in 1...10 {
    if i % 2 == 0 {
        break
    }
    print(i)
}
```

##### Quiz 8: Learn fallthrough

**Description**: Write a switch statement with a case `1` that falls through to the code in case `2`.

**Starting Code**:
```swift
let value = 1
```

**Solution Code**:
```swift
let value = 1
switch value {
case 1:
    print("Case 1")
    fallthrough
case 2:
    print("Case 2")
default:
    print("Other case")
}
```

#### Module 4: Functions

##### Quiz 1: Learn functions

**Description**: Write a function `square` that takes an Int parameter `number` and prints the result.

**Starting Code**:
```swift
square(number: 10)
```

**Solution Code**:
```swift
func square(number: Int) {
    print(number * number)
}
square(number: 10)
```

##### Quiz 2: Learn Argument Labels I

**Description**: Write a function `multiply` that takes two parameters `a` and `b` and returns their product. Use argument labels `number1` and `number2`.

**Starting Code**:
```swift
let result = multiply(number1: 5, number2: 5)
print(result)
```

**Solution Code**:
```swift
func multiply(number1 a: Int, number2 b: Int) -> Int {
    return a * b
}
let result = multiply(number1: 5, number2: 5)
print(result)
```

##### Quiz 3: Learn Argument Labels II

**Description**: Write a function `subtract` that takes two parameters (`a` and `b`) without argument labels and returns the difference.

**Starting Code**:
```swift
let result = subtract(20, 5)
print(result)
```

**Solution Code**:
```swift
func subtract(_ a: Int, _ b: Int) -> Int {
    return a - b
}
let result = subtract(20, 5)
print(result)
```

##### Quiz 4: Learn default Parameter Values

**Description**: Write a function `increment` that has a parameter `number` and an optional parameter `by` (use argument label `incrementValue`), which defaults to 1. The function should increment `number` by the value of `by` and return the result.

**Starting Code**:
```swift
let result = increment(5)
print(result)
```

**Solution Code**:
```swift
func increment(_ number: Int, incrementValue: Int = 1) -> Int {
    return number + incrementValue
}
let result = increment(5)
print(result)
```

##### Quiz 5: Learn variadic Parameters

**Description**: Write a function `sum` that accepts a variable `number` of `Int` values and returns their `sum`.

**Starting Code**:
```swift
let result = sum(1, 2, 3, 4, 5)
print(result)
```

**Solution Code**:
```swift
func sum(_ numbers: Int...) -> Int {
    return numbers.reduce(0, +)
}

let result = sum(1, 2, 3, 4, 5)
print(result)
```

##### Quiz 6: Learn In-Out Parameters

**Description**: Rewrite the function `increment` to accept a new parameter `result`, which saves the result in this variable (`result` should be the last parameter). The function should return nothing.

**Starting Code**:
```swift
func increment(_ number: Int, by incrementValue: Int = 1) -> Int {
    return number + incrementValue
}

var result = 0
increment(5, &result)
print(result)
```

**Solution Code**:
```swift
func increment(_ number: Int, incrementValue: Int = 1, result: inout Int) {
    result = number + incrementValue
}

var result = 0
increment(5, result: &result)
print(result)
```

#### Module 5: Optionals

##### Quiz 1: Learn Bindings

**Description**:
1) Write a function `printName` that accepts an optional string `name`.
2) Use `if let` to bind the unwrapped `name` in a variable called `unwrappedName`.
3) Print the `unwrappedName`.
4) Otherwise print "Name is nil".

**Starting Code**:
```swift
printName("Alice")
printName(nil)
```

**Solution Code**:
```swift
func printName(_ name: String?) {
    if let unwrappedName = name {
        print(unwrappedName)
    } else {
        print("Name is nil")
    }
}
printName("Alice")
printName(nil)
```

##### Quiz 2: Learn Chaining

**Description**:
1) Write a function `getUppercaseName` that accepts an optional string `name` and returns the uppercase version of the name.
2) Use optional chaining to access the String function `uppercased()`.

**Starting Code**:
```swift
...

let uppercasedName = getUppercaseName("Bob")
if let unwrappedUppercasedName = uppercasedName {
    print(unwrappedUppercasedName)
}
```

**Solution Code**:
```swift
func getUppercaseName(_ name: String?) -> String? {
    return name?.uppercased()
}

let uppercasedName = getUppercaseName("Bob")
if let unwrappedUppercasedName = uppercasedName {
    print(unwrappedUppercasedName)
}
```

##### Quiz 3: Learn Nil-Coalescing

**Description**: Write a function `getNameOrDefault` that accepts an optional string `name` and returns the name if it has a value or "Unknown" if it is nil.

**Starting Code**:
```swift
...

let name = getNameOrDefault(nil)
print(name)
```

**Solution Code**:
```swift
func getNameOrDefault(_ name: String?) -> String {
    return name ?? "Unknown"
}

let name = getNameOrDefault(nil)
print(name)
```

##### Quiz 4: Learn Unconditional Unwrapping

**Description**: Write a function `forceUnwrapName` that accepts an optional string `name` and forcefully unwraps and returns the name.

**Starting Code**:
```swift
...

let name = forceUnwrapName("Charlie")
print(name)
```

**Solution Code**:
```swift
func forceUnwrapName(_ name: String?) -> String {
    return name!
}

let name = forceUnwrapName("Charlie")
print(name)
```

#### Module 6: Collection Types

##### Quiz 1: Learn Arrays

**Description**:
1) Create an array `fruits` with the values "Apple", "Banana", and "Cherry".
2) Add "Orange" to the `fruits` array.
3) Remove "Cherry" from the `fruits` array.
4) Change "Apple" to "Mango".
5) Iterate over the `fruits` array and print each element.

**Starting Code**: ...

**Solution Code**:
```swift
var fruits = ["Apple", "Banana", "Cherry"]
fruits.append("Orange")
fruits.remove(at: 2)
fruits[0] = "Mango"
for fruit in fruits {
    print(fruit)
}


```

##### Quiz 2: Learn Sets

**Description**:
1) Create a set `colors` with the values "Red", "Green", and "Blue".
2) Add "Yellow" to the `colors` set.
3) Remove "Red" from the `colors` set.
4) Iterate over the `colors` set and print each element.
5) Create a new set `colors2` with the values "Yellow", "Black", and "Magenta" and combine it with `colors` to a new set `combinedColors`.
6) Iterate over the `combinedColors` set and print each element.

**Starting Code**: ...

**Solution Code**:
```swift
var colors: Set = ["Red", "Green", "Blue"]
colors.insert("Yellow")
colors.remove("Red")
for color in colors {
    print(color)
}
var colors2: Set = ["Yellow", "Black", "Magenta"]
var combinedColors = colors.union(colors2)
for color in combinedColors {
    print(color)
}
```

##### Quiz 3: Learn Dictionaries

**Description**:
1) Create a dictionary `person` with the keys "name", "age", and "city" and the corresponding values "Alice", 30, and "New York".
2) Change the value of the key "city" in the `person` dictionary to "Los Angeles".
3) Remove the value of the key "name" in the `person` dictionary.
4) Iterate over the `person` dictionary and print each key and value.

**Starting Code**: ...

**Solution Code**:
```swift
var person: [String: Any] = ["name": "Alice", "age": 30, "city": "New York"]
person["city"] = "Los Angeles"
person["name"] = nil
for (key, value) in person {
    print("\\(key): \\(value)")
}
```

#### Module 7: Object oriented programming

##### Quiz 1: Learn Classes


**Description**:
1) Define a class `Person` with the properties `name` and `age`.
2) Define a function `printInformations()`, that prints the following text:
"Hello, my name is `name` and I am `age`"
3) Create an instance of the `Person` class with the name "John" and age 18 and call the function `printInformations()`.

**Starting Code**: ...

**Solution Code**:
```swift
class Person {
    var name: String
    var age: Int
    
    init(name: String, age: Int) {
        self.name = name
        self.age = age
    }

    func printInformations() {
        print("Hello, my name is \\(name) and I am \\(age)")
    }
}

let person = Person(name: "John", age: 18)
person.printInformations()
```

##### Quiz 2: Learn Inheritance

**Description**:
1) Create a subclass `Student` that inherits from the `Person` class and has an additional property `grade`.
2) Create an instance of the `Student` class with the name "John", age 18 and grade "A".

Tip: You need to call the function `super.init(name:, age:)` in the initializer to call the superclass.

**Starting Code**:
```swift
class Person {
    var name: String
    var age: Int
    
    init(name: String, age: Int) {
        self.name = name
        self.age = age
    }

    func printInformations() {
        print("Hello, my name is \\(name) and I am \\(age)")
    }
}

...

let student = Student(name: "John", age: 18, grade: "A")
student.printInformations()
```

**Solution Code**:
```swift
class Person {
    var name: String
    var age: Int
    
    init(name: String, age: Int) {
        self.name = name
        self.age = age
    }

    func printInformations() {
        print("Hello, my name is \\(name) and I am \\(age)")
    }
}

class Student: Person {
    var grade: String
    
    init(name: String, age: Int, grade: String) {
        self.grade = grade
        super.init(name: name, age: age)
    }
}

let student = Student(name: "John", age: 18, grade: "A")
student.printInformations()
```

##### Quiz 3: Learn Protocols

**Description**:
1) Define a protocol `Vehicle` with a method `drive`.
2) Create a class `Car` that adopts the `Vehicle` protocol and implements the `drive` method.
3) The method `drive` should print "Driving a car".
4) Create an instance of the `Car` class call the function `drive()`.

**Starting Code**: ...

**Solution Code**:
```swift
protocol Vehicle {
    func drive()
}

class Car: Vehicle {
    func drive() {
        print("Driving a car")
    }
}

let car = Car()
car.drive()
```

##### Quiz 4: Learn Extensions

**Description**:
1) Create an extension for the `String` class that adds a method `reversedString` which returns the reversed string.
2) Call the method `reversedString` with the String "hello" and print the result.

Tip: Use the String method `reversed()`.

**Starting Code**: ...

**Solution Code**:
```swift
extension String {
    func reversedString() -> String {
        return String(self.reversed())
    }
}

print("hello".reversedString())
```

#### Module 8: Error Handling

##### Quiz 1: Learn Errors

**Description**:
1) Define a `LoginError` enumeration that adopts the `Error` protocol and has the cases `invalidUsername` and `invalidPassword`.
2) Write a function `login` that checks a username and password and throws an error if the inputs are invalid.
    2.1) If username is not "admin" throw an error.
    2.2) If password is not "1234" throw an error.
    2.3) Print "Login successful" after both checks.
3) Improve the code below with `do-catch`.

**Starting Code**:
```swift
...

try login(username: "admin", password: "1234")
print("Invalid username")
print("Invalid password")
print("Other error")
```

**Solution Code**:
```swift
enum LoginError: Error {
    case invalidUsername, invalidPassword
}

func login(username: String, password: String) throws {
    if username != "admin" {
        throw LoginError.invalidUsername
    }
    if password != "1234" {
        throw LoginError.invalidPassword
    }
    print("Login successful")
}

do {
    try login(username: "admin", password: "1234")
} catch LoginError.invalidUsername {
    print("Invalid username")
} catch LoginError.invalidPassword {
    print("Invalid password")
} catch {
    print("Other error")
}
```

### Level Advanced

#### Module 9: Functional Programming

##### Quiz 1: Learn Closures

**Description**: Write a simple closure (`add`) that adds two `Int` (`a` and `b`) values and returns the result.

**Starting Code**:
```swift
let add: ... =

let result = add(2, 3)
print(result)
```

**Solution Code**:
```swift
let add: (Int, Int) -> Int = { (a, b) in
    return a + b
}
let result = add(2, 3)
print(result)
```

##### Quiz 2: Learn Capturing Values

**Description**: Write a closure that captures an `Int` variable and increments its value.

**Starting Code**:
```swift
var counter = 0

...

incrementCounter()
print(counter)
```

**Solution Code**:
```swift
var counter = 0
let incrementCounter = {
    counter += 1
}
incrementCounter()
print(counter)
```

##### Quiz 3: Learn Generic Functions

**Description**: Write a generic function `square` that calculates and returns the square of a number.

Tip: `T` must conform to the `Numeric` protocol.

**Starting Code**:
```swift
...

var double = square(2.5)
var integer = square(10)
print(double)
print(integer)
```

**Solution Code**:
```swift
func square<T: Numeric>(_ number: T) -> T {
    return number * number
}

var double = square(2.5)
var integer = square(10)
print(double)
print(integer)
```

#### Module 10: Advanced Swift-Lectures

##### Quiz 1: Learn Property Observers

**Description**:
1) Create a class `BankAccount` with a property `balance` of type `Double`.
2) Use `willSet` and `didSet` observers.
   2.1) `willSet` should print "Balance is about to change to (newValue)".
   2.2) `didSet` should print "Deposited (balance - oldValue) units" if the balance increased, or "Withdrew (oldValue - balance) units" if the balance decreased

.
3) Create an instance `account` and change the balance to 100.0 and to 75.0.

**Starting Code**: ...

**Solution Code**:
```swift
class BankAccount {
    var balance: Double = 0.0 {
        willSet {
            print("Balance is about to change to \\(newValue)")
        }
        didSet {
            if balance > oldValue {
                print("Deposited \\(balance - oldValue) units")
            } else {
                print("Withdrew \\(oldValue - balance) units")
            }
        }
    }
}

let account = BankAccount()
account.balance = 100.0
account.balance = 75.0
```

##### Quiz 2: Learn Type Casting

**Description**: Write a function `describeVehicles` that accepts an array of `Vehicle` objects and prints "Driving a car" for each Car object and "Riding a bike" for each `Bike` object.

**Starting Code**:
```swift
class Vehicle {}
class Car: Vehicle {
    func drive() {
        print("Driving a car")
    }
}
class Bike: Vehicle {
    func ride() {
        print("Riding a bike")
    }
}

let vehicles: [Vehicle] = [Car(), Bike(), Car()]

...

describeVehicles(vehicles: vehicles)
```

**Solution Code**:
```swift
class Vehicle {}
class Car: Vehicle {
    func drive() {
        print("Driving a car")
    }
}
class Bike: Vehicle {
    func ride() {
        print("Riding a bike")
    }
}

let vehicles: [Vehicle] = [Car(), Bike(), Car()]

func describeVehicles(vehicles: [Vehicle]) {
    for vehicle in vehicles {
        if let car = vehicle as? Car {
            car.drive()
        } else if let bike = vehicle as? Bike {
            bike.ride()
        }
    }
}

describeVehicles(vehicles: vehicles)
```

## Learn SwiftUI

...
```

Diese Markdown-Datei enthält die Quizzes im gleichen Layout wie zuvor. Wenn du noch weitere Inhalte oder Änderungen hinzufügen möchtest, lass es mich wissen!
