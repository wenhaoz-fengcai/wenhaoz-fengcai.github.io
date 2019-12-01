# CS131, Spring19 -- Discussion 1B

Week 9 (05/31/19)

## Administrations

1. TA: Wenhao Zhang (wenhaoz@cs.ucla.edu)
2. Office hour:
   - Time: 9:30am ~ 11:30am, Monday
   - Location: 3rd floor, common area in Eng VI
3. Class Announcements
   - Project ddl extends to **Monday (06/03/2019), 11:55pm**
   - HW6 dues on **2019-06-07** (Next Friday)
4. Today's agenda
   - Tensorflow
   - Intro to Kotlin
   - HW6 



## TensorFlow

- Library for symbolic mathematics and neural networks
- Initially meant for Google’s internal use, released for the public 2015
- Easy to define neural networks, TensorFlow takes care of running it efficiently on multiple CPUs or GPUs
 

### TensorFlow Bindings

Bindings allow you to call another language’s code

- Usually high-level languages (Python, Java, ...) call low-level libraries (C, C++, ...)
- TensorFlow’s focus has been on Python, but there are bindings for other languages as well
    * JavaScript, C++, Java, Go, Swift, C#, Scala, Ocaml


```python
import tensorflow as tf
mnist = tf.keras.datasets.mnist # 28x28 images of hand-written digits 0-9

(x_train, y_train), (x_test, y_test) = mnist.load_data()

x_train = tf.keras.utils.normalize(x_train, axis=1)
x_test = tf.keras.utils.normalize(x_test, axis=1)

model = tf.keras.models.Sequential()
model.add(tf.keras.layers.Flatten())
model.add(tf.keras.layers.Dense(128, activation=tf.nn.relu))
model.add(tf.keras.layers.Dense(128, activation=tf.nn.relu))
model.add(tf.keras.layers.Dense(10, activation=tf.nn.softmax))

model.compile(optimizer='adam',
                loss='sparse_categorical_crossentropy',
                metrics=['accuracy'])

model.fit(x_train, y_train, epochs=3)

val_loss, val_acc = model.evaluate(x_test, y_test)
print(val_loss, val_acc)

import matplotlib.pyplot as plt

plt.imshow(x_train[0], cmap=plt.cm.binary)
plt.show()
print(x_train[0])

model.save('epic_num_read.model')
new_model = tf.keras.models.load_model('epic_num_read.model')

predictions = new_model.predict([x_test])

import numpy as np

print(np.argmax(predictions[0]))

plt.imshow(x_test[0])
plt.show()
```

## Kotlin

### Features

1. Cross-platform, statically typed, general-purpose programming language with type inference.
2. Designed to interoperate fully with Java with much more concise syntax
3. Runs on JVM; Mainly target the JVM, but also compiles to Javascript or native code.
4. Sponsored by JetBrains and Google through Kotlin Foundation. 
5. Open-source under Apache 2 license.

### Why Kotlin

1. Concise
    - Drastically reduce the amount of boilerplate code
2. Safe
    - Avoid entire classes of errors such as null pointer exceptions
3. Interoperable
    - Leverage existing libraries for JVM, Android, and the browser.
4. Tool supports
    - IntelliJ
    - Eclipse
    - Android Studio
    - Terminal

### Hello World (simplest version)

```kotlin
fun main(){
    println("Hello World")
}
```

### Things to remember

- Semicolons are optional as a statement terminator.
- Kotlin variables can be immutable, declared with `val` keyword, or mutable, declared with the `var` keyword.
- Class memebers are public by default, and classes are final by default, meaning that creating a subclass is disabled unless the base class is declared with the `open` keyword

### Basics

#### Defining functions

Function having two Int parameters with Int return type:

```kotlin
fun sum(a: Int, b: Int): Int {
    return a + b
}

/*Driver code*/
fun main() {
    print("sum of 3 and 5 is ")
    println(sum(3, 5))
}
```
The output should be

> sum of 3 and 5 is 8

Function with an expression body and inferred return type:
``` kotlin
fun sum(a: Int, b: Int) = a + b
```
#### Defining variables

- `val`: immutable vars
- `var`: mutable vars

Read-only local variables are defined using the keyword val. They can be assigned a value only once.

```kotlin
fun main() {
    val a: Int = 1  // immediate assignment
    val b = 2   // `Int` type is inferred
    val c: Int  // Type required when no initializer is provided
    c = 3       // deferred assignment
    println("a = $a, b = $b, c = $c")
}
```

Variables that can be reassigned use the var keyword:
```kotlin
fun main() {
    var x = 5 // `Int` type is inferred
    x += 1
    println("x = $x")
}
```

Global vars
```kotlin
val PI = 3.14
var x = 0

fun incrementX() { 
    x += 1 
}

fun main() {
    println("x = $x; PI = $PI")
    incrementX()
    println("incrementX()")
    println("x = $x; PI = $PI")
}
```

#### Lambda function

Lambda functions defined with curly braces: `{ arg : argType -> expression }`

```kotlin
{s:String -> println(s)}("Hello world!")
```
 
#### List

List in kotlin can be heterogenous.

```kotlin
fun main(args: Array<String>) {
    val myList = listOf(1, 2, 3, 4)
    print(myList.map { x -> x*2 })
}
```

```kotlin
fun main(args: Array<String>) {
    val myList = listOf(1, 2, 3, 4)
    println(myList.map { it*2 }) // `it` is the iterator
}
```

## HW6

- Review TensorFlow Architecture and TensorFlow in other languages, and consider three other languages that are plausible candidates for implementing your application: 
    * Java
    * OCaml
    * Kotlin
- Compare these to each others and Python
- 3-page executive summary
- Evaluate these three languages as alternatives to Python when building the proxy server herd in course project.
- Unlike the project, we are not expecting working prototypes, though prototypes are welcome.
- Focus on “ease of use, flexibility, generality, performance, reliability”
- Cite your sources
- Write a function `everyNth(L, N)`
    * Returns a new list that contains every Nth element of list L
    * E.g. List=[1,2,3,4,5,6], N=2 => [2,4,6]
