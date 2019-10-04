# Optionals lab

Fork and clone this repo. On your fork, answer and commit the follow questions. When you are finished, submit the link to your repo on Canvas.


## Question 1

a. Given the variable `userNameOne` below, print *"The username is Test User"*.  Use *Optional Binding* (`if let`) to print the name.

```swift
var userNameOne: String? = "Test User"
```swift
if let userNameOne = "Test User" {
print(userNameOne)
}
```

b. Given the variable `userNameTwo` below, print *"The username is undefined"*.  Use the *nil coalescing operator* (`??`).

```swift
var userNameTwo: String? = nil
```swift
print("The username is \(userNameTwo ?? "undefined")")
```

## Question 2

a. Given the variables `rectOneWidth` and `rectOneHeight` below, print "The area of rectOne is 50".  Use *Optional Binding* (`if let`) to print the area.

```swift
var rectOneWidth: Double? = 5
var rectOneHeight: Double? = 10
```
```swift
if let rectWidth = rectOneWidth {
    if let rectHeight = rectOneHeight {
        let rectArea = rectWidth * rectHeight
        print("The area of rectOne is \(rectArea)")
    }
}
```

b. Given the variables `rectTwoWidth` and `rectTwoHeight` below, print "The are of rectTwo is not able to be calculated".  Use *Optional Binding* (`if let`) to print this message.

```swift
var rectTwoWidth: Double? = nil
var rectTwoHeight: Double? = nil
```
```swift
if let rectWidth = rectTwoWidth {
    if let rectHeight = rectTwoHeight {
        let rectArea = rectHeight * rectWidth
        print("rectTwo area is \(rectArea)")
    } else {
        print("The are of rectTwo is not able to be calculated")
    }
} else {
    print("The are of rectTwo is not able to be calculated")
}
```

## Question 3

a. Given the variables `userOneName`, `userOneAge`, and `userOneHeight` below, write code that prints "Hello Anne!  You are 15 years old and 5.8 feet tall" (1 foot = 12 inches).  Use optional binding.


```swift
var userOneName: String? = "Anne"
var userOneAge: Int? = 15
var userOneHeight: Double? = 70
```
```swift
if let userName = userOneName {
    if let userAge = userOneAge {
        if let userHeight = userOneHeight {
            let userHeight = round(10 * (userHeight/12.0)) / 10
            print("Hello \(userName)!  You are \(userAge) years old and \(userHeight) feet tall")
        }
    }
}
```

b. Given the variables `userTwoName`, `userTwoAge` and `userTwoHeight` below, write code that prints "Hello user!  You are 15 years old and I don't know how tall you are".  Use optional binding

```swift
var userTwoName: String? = nil
var userTwoAge: Int? = 15
var userTwoHeight: Double? = nil
```
```swift
    if let userAge = userTwoAge {
        if let userHeight = userTwoHeight {
            if let userName = userTwoName {
            let userHeight = round(10 * (userHeight/12.0)) / 10
            print("Hello \(userName)!  You are \(userAge) years old and \(userHeight) feet tall")
        }
        } else {
            print(" Hello user!  You are 15 years old and I don't know how tall you are")
    }
}
```

## Question 4

Give the variable `favoriteNumber`, write code that either prints "Your favorite number is " followed by the number, or "I don't know what your favorite number is"

`favoriteNumber` is of type Int? and will either be `nil` or a random number between 0 and 10.  It will change each time you run your Playground.

```swift
var favoriteNumber = Bool.random() ? Int.random(in: 0...10) : nil
```
```swift
if let number = favoriteNumber {
    print("Your favorite number is \(number)")
} else {
    print("I don't know what your favorite number is")
}

```


## Question 5

Given the variables `numOne`, `numTwo` and `numThree`, write code that prints "The sum of all the numbers is " followed by their sum.  If a number is `nil`, don't add it to the sum.  If all numbers are `nil`, the sum is zero.

```swift
var numOne = Bool.random() ? Int.random(in: 0...10) : nil
var numTwo = Bool.random() ? Int.random(in: 0...10) : nil
var numThree = Bool.random() ? Int.random(in: 0...10) : nil
```
```swift
var sum = 0
sum += numOne ?? 0
sum += numTwo ?? 0
sum += numThree ?? 0
print("The sum of all the numbers is \(sum)")
```

## Question 6

a. Given the variable `numbers` below, write code that prints "The sum of all the numbers is " followed by their sum.  If a number is `nil`, don't add it to the sum.  If all numbers are `nil`, the sum is zero.

```swift
var numbers = [Int?]()

for _ in 0..<10 {
    numbers.append(Bool.random() ? Int.random(in: 0...100) : nil)
}
```
```swift
var sum = 0
for each in numbers {
    if each != nil {
        sum += each!
    }
}
print("The sum of all the numbers is \(sum)")
```

b. Using the same variable, find the average of all non-nil values.
```swift
func averageOfAll(_: [Int?]) -> Int? {
var nilCount = 0
var sum = 0
for each in numbers {
    if each != nil {
        sum += each!
    } else {
        nilCount += 1
    }
}
    let average = sum / (numbers.count - nilCount)
    return average
}
print("The average of numbers is: \(averageOfAll(numbers)!)")
```

## Extra Questions

https://github.com/joinpursuit/Pursuit-Core-iOS-Extra-Optionals-Questions/blob/master/README.md
