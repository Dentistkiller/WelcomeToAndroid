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


# Android XML Layouts & Components Cheat Sheet

This cheat sheet provides an overview of Android XML layouts and common UI components. It includes examples of different layouts, attributes, and other useful XML elements for Android development.

---

## 📐 1. **Common Layout Types**

### 1.1 **LinearLayout**
- Arranges child views in a **vertical** or **horizontal** sequence.

```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello LinearLayout!" />

</LinearLayout>
```

### 1.2 **RelativeLayout**
- Positions child views **relative** to each other or the parent.

```xml
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/title"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello RelativeLayout!" />

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Click Me"
        android:layout_below="@id/title" />

</RelativeLayout>
```

### 1.3 **ConstraintLayout**
- Flexible layout with powerful constraints for complex designs.

```xml
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:id="@+id/titleText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello ConstraintLayout!"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

### 1.4 **FrameLayout**
- Stacks child views **on top** of each other.

```xml
<FrameLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <ImageView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:src="@drawable/background" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Overlay Text" />

</FrameLayout>
```

### 1.5 **GridLayout**
- Organizes child views into **rows and columns**.

```xml
<GridLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:columnCount="2">

    <TextView
        android:layout_column="0"
        android:text="Item 1" />

    <TextView
        android:layout_column="1"
        android:text="Item 2" />

</GridLayout>
```

---

## 📊 2. **Common XML UI Components**

### 2.1 **TextView**
- Displays **text** on the screen.

```xml
<TextView
    android:id="@+id/myTextView"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Hello, World!"
    android:textSize="20sp"
    android:textColor="#FF0000" />
```

### 2.2 **EditText**
- Allows users to **input text**.

```xml
<EditText
    android:id="@+id/editText"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:hint="Enter your name" />
```

### 2.3 **Button**
- Used to trigger **actions** when clicked.

```xml
<Button
    android:id="@+id/button"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Submit" />
```

### 2.4 **ImageView**
- Displays **images** from drawable resources or URLs.

```xml
<ImageView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:src="@drawable/ic_launcher" />
```

### 2.5 **CheckBox**
- Provides a **checkable** option.

```xml
<CheckBox
    android:id="@+id/checkBox"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="I agree" />
```

### 2.6 **RadioButton & RadioGroup**
- Allows **exclusive selection** among multiple options.

```xml
<RadioGroup
    android:layout_width="wrap_content"
    android:layout_height="wrap_content">

    <RadioButton
        android:id="@+id/radio1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Option 1" />

    <RadioButton
        android:id="@+id/radio2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Option 2" />

</RadioGroup>
```

### 2.7 **Switch**
- Toggle **on/off** state.

```xml
<Switch
    android:id="@+id/switch"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Enable Feature" />
```

### 2.8 **SeekBar**
- Selects a **value** within a range.

```xml
<SeekBar
    android:id="@+id/seekBar"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:max="100" />
```

### 2.9 **Spinner**
- Dropdown menu for **item selection**.

```xml
<Spinner
    android:id="@+id/spinner"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" />
```

### 2.10 **ProgressBar**
- Indicates **progress** for tasks.

```xml
<ProgressBar
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:indeterminate="true" />
```

---

## 🔍 3. **Useful XML Attributes**

| Attribute            | Description                        |
|----------------------|------------------------------------|
| `android:id`         | Unique identifier for the view     |
| `android:text`       | Text content for views             |
| `android:textSize`   | Font size (e.g., `20sp`)           |
| `android:layout_width`| Width of the view (`match_parent`) |
| `android:layout_height`| Height of the view (`wrap_content`) |
| `android:padding`    | Inner spacing (e.g., `16dp`)       |
| `android:gravity`    | Content alignment (`center`)       |

This guide should provide a strong foundation for working with Android XML layouts and UI components. 🚀



## 📚 Resources

- [Kotlin Official Documentation](https://kotlinlang.org/docs/home.html)
- [Android Developer Guide](https://developer.android.com/docs)

---

🚀 Happy Coding with Kotlin!

