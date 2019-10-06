# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

a. Given the variable `userNameOne` below, print *"The username is Test User"*.  Use *Optional Binding* (`if let`) to print the name.

```swift
var userNameOne: String? = "Test User"
```
```
Question 1a Answer

if let userNameOne = userNameOne {
    print("The username is \(userNameOne)")
    } else {
    print("There username has no value")
}
```
b. Given the variable `userNameTwo` below, print *"The username is undefined"*.  Use the *nil coalescing operator* (`??`).

```swift
var userNameTwo: String? = nil
```
```
Question 1b Answer

print(userNameTwo ?? "The username is undefined")

```


## Question 2

a. Given the variables `rectOneWidth` and `rectOneHeight` below, print "The area of rectOne is 50".  Use *Optional Binding* (`if let`) to print the area.

```swift
var rectOneWidth: Double? = 5
var rectOneHeight: Double? = 10
```

```
Question 2a Answer

if let rectOneWidth = rectOneWidth {
    if let rectOneHeight = rectOneHeight {
        print("The area of rectOne is \(rectOneWidth * rectOneHeight).")
    }
    else{
        print("rectOneHeight does not contain a valid value.")
    }
} else {
    print ("rectOneWidth does not contain a valid value.")
}

```

b. Given the variables `rectTwoWidth` and `rectTwoHeight` below, print "The area of rectTwo is not able to be calculated".  Use *Optional Binding* (`if let`) to print this message.

```swift
var rectTwoWidth: Double? = nil
var rectTwoHeight: Double? = nil
```

```
Question 2b Answer

if let rectTwoWidth = rectTwoWidth, let rectTwoHeight = rectTwoHeight {
        print("The area of rectTwo is \(rectTwoWidth * rectTwoHeight).")
} else {
    print ("The area of rectTwo is not able to be caluclated.")
}

```

## Question 3

a. Given the variables `userOneName`, `userOneAge`, and `userOneHeight` below, write code that prints "Hello Anne!  You are 15 years old and 5.8 feet tall" (1 foot = 12 inches).  Use optional binding.


```swift
var userOneName: String? = "Anne"
var userOneAge: Int? = 15
var userOneHeight: Double? = 70
```

```
Question 3a Answer

if let userOneName = userOneName, let userOneAge = userOneAge, let userOneHeight = userOneHeight{
    print("Hello \(userOneName)! You are \(userOneAge) years old and \(String(format: "%.2f", userOneHeight/12)) feet tall.")
} else {
    print("One or more pieces of information is invalid.")
}

```

b. Given the variables `userTwoName`, `userTwoAge` and `userTwoHeight` below, write code that prints "Hello user!  You are 15 years old and I don't know how tall you are".  Use optional binding

```swift
var userTwoName: String? = nil
var userTwoAge: Int? = 15
var userTwoHeight: Double? = nil
```

```
Question 3b Answer

if let userTwoAge = userTwoAge{
    if let userTwoName = userTwoName {
        if let userTwoHeight = userTwoHeight{
            print("Hello \(userTwoName)! You are \(userTwoAge) years old and \(String(format: "%.2f", userTwoHeight/12)) feet tall.")
            } else{
                print("One or more pieces of information is invalid")
            }
    } else{
        print("Hello user! You are \(userTwoAge) years, and I do not know how tall you are.")
    }
} else {
    print("One or more pieces of information is invalid.")
}

```


## Question 4 

Given the variable `favoriteNumber`, write code that either prints "Your favorite number is " followed by the number, or "I don't know what your favorite number is"

`favoriteNumber` is of type Int? and will either be `nil` or a random number between 0 and 10.  It will change each time you run your Playground.

```swift
var favoriteNumber = Bool.random() ? Int.random(in: 0...10) : nil
```
```
Question 4 Answers

if let favoriteNumber = favoriteNumber{
    print("Your favourite number is \(favoriteNumber)")
} else {
    print("I don't know what your favourite number is.")
}

```


## Question 5

Given the variables `numOne`, `numTwo` and `numThree`, write code that prints "The sum of all the numbers is " followed by their sum.  If a number is `nil`, don't add it to the sum.  If all numbers are `nil`, the sum is zero.

```swift
var numOne = Bool.random() ? Int.random(in: 0...10) : nil
var numTwo = Bool.random() ? Int.random(in: 0...10) : nil
var numThree = Bool.random() ? Int.random(in: 0...10) : nil
```

```
Question 5 Answer

var sum: Int?

sum = (numOne ?? 0) + (numTwo ?? 0) + (numThree ?? 0)

if let sum = sum {
    print("The sum of all the numbers is \(sum).")
} else {
    print("The sum of all the numbers is 0.")
}
```

## Question 6

a. Given the variable `numbers` below, write code that prints "The sum of all the numbers is " followed by their sum.  If a number is `nil`, don't add it to the sum.  If all numbers are `nil`, the sum is zero.

```swift
var numbers = [Int?]()

for _ in 0..<10 {
    numbers.append(Bool.random() ? Int.random(in: 0...100) : nil)
}
```
```
Question 6a Answer

var sum = 0

for num in numbers{
    guard let num = num else{
        continue
    }
    sum += num
}

if sum == 0 {
        print("The sum of all the numbers is 0.")
    } else {
        print("The sum of all the numbers is \(sum).")
}
```

b. Using the same variable, find the average of all non-nil values.

```
Question 6a Answer

var sum = 0
var numberOfNonNils = 0

for num in numbers{
    guard let num = num else{
        continue
    }
    sum += num
    numberOfNonNils += 1
}

if sum == 0 {
        print("The average of all non-nil values is 0.")
    } else {
        print("The of all non-nil values is \(sum / numberOfNonNils).")
}
```

## Extra Questions

https://github.com/joinpursuit/Pursuit-Core-iOS-Extra-Optionals-Questions/blob/master/README.md
