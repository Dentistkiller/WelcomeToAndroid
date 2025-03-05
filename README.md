# 📱 Kotlin for Mobile Development - Cheat Sheet

A handy reference for learning Kotlin while building Android apps!

## 🟢 Basics

```kotlin
// Variables
val name: String = "Kotlin"   // Immutable (like C#'s 'readonly')
var age: Int = 25             // Mutable

// Type Inference
val greeting = "Hello"  // Type is inferred automatically

// Null Safety
var nullable: String? = null  // Use "?" to allow nulls

// String Interpolation
println("Hello, $name! You are $age years old.")

// Functions
fun add(a: Int, b: Int): Int {
    return a + b
}

// Single-expression function
fun subtract(a: Int, b: Int) = a - b
```

## 🔄 Control Flow

```kotlin
// If-Else Expression
val max = if (a > b) a else b

// When (Switch Alternative)
when (age) {
    in 0..17 -> println("Minor")
    18 -> println("Just 18!")
    else -> println("Adult")
}

// For Loop
for (i in 1..5) println(i)        // Inclusive range
for (i in 1 until 5) println(i)   // Exclusive range

// While Loop
var x = 5
while (x > 0) {
    println(x--)
}
```

## 🧱 Classes & Objects

```kotlin
// Class Declaration
class Person(val name: String, var age: Int) {
    fun greet() = println("Hi, I'm $name!")
}

// Object Instantiation
val person = Person("Alice", 30)
person.greet()

// Data Class (Auto-generates equals(), hashCode(), toString())
data class User(val id: Int, val name: String)

// Inheritance
open class Animal { open fun sound() = println("Animal sound") }
class Dog : Animal() { override fun sound() = println("Woof!") }
```

## 📱 Android Essentials

```kotlin
// Activity Basics
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val button: Button = findViewById(R.id.myButton)
        button.setOnClickListener {
            Toast.makeText(this, "Button Clicked!", Toast.LENGTH_SHORT).show()
        }
    }
}

// Intent (Navigation Between Activities)
val intent = Intent(this, SecondActivity::class.java)
intent.putExtra("KEY", "Value")
startActivity(intent)
```

## 📊 Collections

```kotlin
// Lists
val numbers = listOf(1, 2, 3)       // Immutable
val mutableNumbers = mutableListOf(1, 2, 3)

// Maps
val map = mapOf("name" to "Kotlin", "year" to 2011)

// Looping Through Collections
numbers.forEach { println(it) }
```

## 🔥 Coroutines (Asynchronous Work)

```kotlin
// Launching a Coroutine
GlobalScope.launch {
    delay(1000L)  // Suspend function
    println("Coroutine done!")
}
```

## 📚 Resources

- [Kotlin Official Documentation](https://kotlinlang.org/docs/home.html)
- [Android Developer Guide](https://developer.android.com/docs)

---

🚀 Happy Coding with Kotlin!

