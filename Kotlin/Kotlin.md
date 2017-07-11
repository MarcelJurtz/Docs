# Kotlin

## Programmstart

Einstiegspunkt eines Kotlin-Programms ist eine Funktionn namens *main*.
Dieser wird ein Parameter übergeben, der beliebige Kommandozeilen-Argumente enthält.

```Kotlin
fun main(args: Array<String>) {
  // Code..
}
```

## Kommentare

```Kotlin
// Single line comment

/*
  Multi line comment
*/
```

## Variablen und Konstanten

Variablen werden mit *var* deklariert, Kontstanten mit *val*.

```Kotlin
var variable = 3
val constant = 42
```

Kotlin erkennt in den meisten Fällen den Typ einer Variable, sodass dieser nicht immer explizit gesetzt werden muss. Explizite Typisierung ist dennoch folgendermaßen möglich:

```Kotlin
var variable: Int = 10
```

### Strings

```Kotlin
var aString = "Hello World!"
var bString = "String\nWith a linebreak"
var cString = "String\tWith a tab"

// Template expressions
var name = "Marcel"
var message = "Hello $name, your name has ${message.length} characters"
```

#### Raw Strings

Raw Strings können beliebige Zeichen enthalten, beispielsweise Zeilenumbrüche:

```Kotlin
val rawString = """
  fun helloWorld(val name: String) {
    println("Hello, $name!")
  }
"""
```

## Null

Damit eine Variable den Wert Null besitzen kann, muss sie explizit entsprechend gekennzeichnet werden. Dies wird durch anhängen eines Fragezeichens an den Typ erreicht. Dieser Operator muss auch bei Zugriffen verwendet werden.

```Kotlin
var nullableString: String? = "Hello"
var length = nullableString?.length
```

Sollte der Wert der Variablen Null sein, so kann direkt ein alternativer Wert angegeben werden:

```Kotlin
var length = nullableString?.length ?: -1
// length = 3
```

Die Variable *length* besitzt den Wert *-1*, wenn *nullableString* Null ist.

```Kotlin
var nullableString: String? = null
var length = nullableString?.length ?: -1
// length = -1
```

## Funktionen

Funktionen werden mit dem Keyword *fun* deklariert. Argumente werden mithilfe der Klammern nach dem Funktionsnamen angegeben und können einen  Standardwert besitzen. Der Rückgabewert der Funktion (falls vorhanden) folgt nach der Parameterangabe.

```Kotlin
fun sayHello(name: String = "NoName"): String {
  return "Hello, $name!"
}

println(hello("Marcel")) // Hello, Marcel!
println(hello()) // Hello, NoName
```

Es kann eine variable Anzahl an Argumenten übergeben werden, wenn die Funktion mit dem Keyword *vararg* gekennzeichnet wird:

```Kotlin
fun varargsDemo(vararg items: Int) {
  println("${items.size} elements were given")
}

varargsDemo() // 0 elements were given
varargsDemo("Test", "Sample") // 2 elements were given
```

Funktionen, die nur aus einer Zeile Code bestehen, können ohne geschweifte Klammern geschrieben werden (stattdessen folgt der Methodenrumpf nach einem Gleichheitszeichen):

```Kotlin
fun even(x: Int): Boolean = x % 2 == 0

println(even(1)) // false
println(even(2)) // true
```

Wenn der Typ des Rückgabewerts keine Alternativmöglichkeiten zulässt, kann die Angabe dessen vernachlässigt werden:

```Kotlin
fun even(x: Int) = x % 2 == 0

println(even(1)) // false
println(even(2)) // true
```

### Verschachtelte Funktionen

Funktionen können Funktionen als Argumente verwenden, sowie Funktionen zurückgeben:

TODO

## Klassen

Klassen werden mit dem Keyword *class* deklariert.  
Instanziiert wird diese per Konstruktor, Kotlin besitzt aber kein *new*-Keyword!

```Kotlin
class SampleClass(val prop: Int) {
  fun add(y: Int): Int {
    return x + y
  }

  infix fun multiply(y: Int): Int {
    return x*y
  }
}

// Instantiating
var instance = SampleClass(13)

println(instance.add(29)) // 42
```

### Infix-Notation

Wurde eine Funktion mit dem Keyword *infix*-markiert, kann diese per Infix-Notation aufgerufen werden:

```Kotlin
println(instance multiply 12) // 25
```

## Packages

Packages funktionieren wie in Java:

```Kotlin
package com.marceljurtz.hellokotlin
```

## Links

* [From Java to Kotlin](https://fabiomsr.github.io/from-java-to-kotlin/index.html)
* [Learn X in Y Minutes - Kotlin](https://learnxinyminutes.com/docs/kotlin/)
