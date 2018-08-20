# Overview

Online playground https://try.kotlinlang.org/. Includes code from Kotlin in Action and allows converting of Java code to Kotlin code. Koans are exercises similar to code kata.

## Materials

Official reference: https://kotlinlang.org/docs/reference/


# IDE

IntelliJ IDEA is recommended as IDE, and Gradle as build tool (instead of Maven).

## Creating New Project

IDEA -> New Project -> Gradle -> Java + Kotlin (Java) (check both)

Note: check Gradle, Kotlin installation

## Variables

var - mutable declaration
val - immutable declaration

```
var variable = "String value"
val variable = "String value"
val number = 3.14

// With type definition
var typed: String = "String value"
```

Types are identical to Java Types (Double, Float, Int, Long, Byte, String and etc.)

Underscores could be used for numbers
```
val number = 123_456_789
val theSameNumber = 123456789
```

Type conversion:
```
val intNumber = 123;
var longNumber = intNumber.toLong()
```

## Comments

End of line commment:
```
// comment
```

Block comment
```
/*
  comment
*/
```

## Control flow

Java
```
int lowest = (a < b) ? a : b;
```

Kotlin
```
val lowest = if (a < b) a else b

var lowest = if (a < b) {
    // multiple statements
    a
} else {
    // multiple statements
    b
}
```

```
val burgersOrdered = 1

when (burgersOrders) {
   0 -> println("Not hungry")
   1 -> println("Hungry")
   2, 3, 4 -> pritnln("Very hungry")
   Math.abs(burgersOrders) -> println("Expression")
   in 5..7 -> println("Range value")
   else -> {
       println("Are you sure")
   }
}

while (a < b) {
    // statements
}

do {

} while (a < b)

```

For loop

```
for (item in 1..10) {
    // item is immutable
}

for (ch in "string value") {
    // iterate over letters
}
```

For loop with index
```
for ((index, item) in 5..7) {
    // index - will be index position starting from 0
    // item will be action value
}
```

## Functions

Unit - is return type for Java void.

Define functions
```
fun newFunction(param1: Int, param2: Int): Int {
    return param1 + param2
}
```

Short return definition
```
fun function1(param1: Int): Int = param1 * 2
```

Default values
```
fun function2(param1: Int = 2) {

}
```

## Package

Kotlin does default imports (kotlin.*, kotlin.collections.* and etc)

## Classes

```
class Person(firstName: String, lastName: String) {
    init {
        println("Creating class ")
    }

    // second constructor
    constructor(firstName: String):
        this(firstName, "Default Last Name") {
    }
}

val person = Person("First", "Last")
```

Set class visibility
```
class Person internal constructor(firstName: String, lastName: String) {
    ...
}
```

Create object, add attributes and functions
```
val location = object {
    var x = 200
    var y = 200

    fun printId() {
        println("$x")
    }
}
```

## Interfaces

```
interface Vehicle {
    val  MakeName: String

    fun go() {
        println("value")
    }

    fun stop() {
        println("value")
    }

    fun getMpg(): Int {
        return 50
    }

    fun getDoors(): Int
}

class Car: Vehicle {
    override val MakeName = "Ford"

    override fun getDoors(): Int {
        return 5
    }
}
```

## Generics

Generic functions
```
fun <T> max(param1:: T, param2: T): T {
    val result = param1.compareTo(param2)

    return if (result > 0) param2 else param2
}
```

## Operators overloading

Binary operations: + - * / % ..

".." - range operator

Unary operators: ++x, x++, --x, x--, +x (unary plus), -x (unary minus), !x

```
// overload operator
operator fun plus(other: Position): Position {
    return ...
}
```

## Annotations

```
@Deprecated("Use something else", ReplaceWith("New Type"))
class Person {

}
```

## DSL

Domain specific language typically focuses on specific domain.


## Infix notation
Functions marked with the infix keyword can also be called using the infix notation.

https://kotlinlang.org/docs/reference/functions.html#infix-notation

```
infix fun Int.shl(x: Int): Int { ... }
​
// calling the function using the infix notation
1 shl 2
​
// is the same as
1.shl(2)
```

## Lambda Functions

```
val names = collection.map { a -> a.name }
```

## Method chaining

Example:
```
val students = getStudents();
var collection = students.drop(1).take(3).toList();
```