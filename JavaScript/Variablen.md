# Variablen

## Deklaration

```JavaScript
var var1 = 5;
let var2 = 13;
```

Definition mit den Keywords ```var``` oder ```let```. Let wird seit ES6 unterstützt und muss durch Einbinden des strikten Modus aktiviert werden:

```JavaScript
'use Strict';
```

## Datentypen

Differenzierung zwischen sechs Variablentypen:
* Primitive Datentypen:
  * Zahlen
  * Zeichenketten
  * Boolesche Wahrheitswerte
* null
* undefined
* object

### Zahlen

Verwendung verschiedener Zahlensysteme möglich.

```JavaScript
let number1 = 0b11010011; // Präfix 0b für Binärzahlen
let number2 = 050; // Präfix 0 für Oktalzahlen
// (Interpretation als Dezimalzahl falls ungültige Zahlen enthalten sind)
let number3 = 0xF; // Präfix 0x Hexadezimalzahlen
```

#### Wertebereiche

Wertebereiche durch Konstanten abrufbar:
```JavaScript
console.log(Number.MIN_VALUE);
console.log(Number.MAX_VALUE);

// Bei Überschreitung des Wertebereichs wird Unendlich verwendet
console.log(Number.POSITIVE_INFINITY);
console.log(Number.NEGATIVE_INFINITY);
```

Ungültige Berechnungen liefern den Rückgabewert NaN (Not a Number).

### Zeichenketten

Definition mit einfachen und doppelten Anführungszeichen möglich:

```JavaScript
let firstname = 'Max';
let lastname = "Mustermann";
```

Um innerhalb einer Zeichenkette Anführungszeichen verwenden zu können, muss entweder die entsprechend andere Form gekapselt werden oder per ```\``` maskiert werden.

```JavaScript
console.log('Hallo "Max Mustermann"');
console.log("Hallo 'Max Mustermann'");

console.log("Hallo \"Max Mustermann\"");
console.log('Hallo \'Max Mustermann\'');
```

#### Escape-Sequenzen

Neben der Maskierung der Anführungszeichen gibt es die folgenden weiteren:

|  Zeichen  |  Bedeutung       |
|-----------|------------------|
| \n        | Neue Zeile       |
| \t        | Tabulator        |
| \b        | Backspace        |
| \r        | Carriage Return  |
| \f        | Seitenvorschub   |

Um nicht in der Konsole, sondern direkt in HTML-Elementen einen Zeilenumbruch darzustellen,
muss anstatt dem ```\n``` ein ```<br/>``` verwendet werden.

### Boolesche Wahrheitswerte

```JavaScript
let bool1 = true;
let bool2 = false;
```

Die klassischen Booleschen Operatoren sind bei JavaScript nicht nur auf Boolesche Wahrheitswerte anwendbar, sondern auch auf nicht-boolesche Operanden.

* AND
  * Wenn der erste Operand ein Objekt ist, wird als Rückgabewert der zweite Operand zurückgegeben.
  * Wenn der erste Operand ```true``` ist (oder wird), und der zweite Operand ein Objekt ist, wird dieses zurückgegeben.
  * Wenn einer der Operanden ```null``` ist, wird ```null``` zurückgegeben.
  * Wenn einer der Operanden ```NaN``` ist, wird ```NaN``` zurückgegeben.
  * Wenn einer der Operanden ```undefined``` ist, wird ```undefined``` zurückgegeben.
* OR
  * Wenn der erste Operand ein Objekt ist, wird dieses zurückgegeben.
  * Wenn der erste Operand zu false evaluiert, wird der zweite Parameter zurückgegeben.
  * Wenn beide Operanden ```null``` sind, wird ```null``` zurückgegeben.
  * Wenn beide Operanden ```NaN``` sind, wird ```NaN``` zurückgegeben.
  * Wenn beide Operaden ```undefined``` sind, wird ```undefined``` zurückgegeben.
* NOT
  * Für eine leere Zeichenkette wird ```true``` zurückgegeben, für eine nicht leere ```false```.
  * Für alle Zahlen außer 0 (inklusive INFINITY) wird false zurückgegeben, für 0 ```true```.
  * Für Objekte wird ```false``` zurückgegeben.
  * Für ```null```, ```NaN``` und ```undefined``` wird ```true``` zurückgegeben.


### Undefined

Variablen, denen kein Wert zugewiesen wurde, erhalten ```undefined``` als Standardwert.

### Null

Null repräsentiert ein leeres Objekt.
Null ist im Gegensatz zu undefined dafür gedacht, manuell vergeben zu werden.

## Vergleiche

Es stehen die üblichen Vergleichsoperatoren zur Verfügung.

Vergleich:
* ```==``` - Gleichheit, prüft Wert (42 == '42' -> true)
* ```!= ``` - Ungleichheit, prüft Wert

Strikter Vergleich:
* ```===``` - strikte Gleichheit, prüft Wert und Datentyp (42 == '42' -> false)
* ```!== ``` - strikte Ungleichheit, prüft Wert und Datentyp

Die Verwendung der strikten Vergleiche verhindert die implizite Typenkonvertierung,
die oft schwer auffindbare Fehler verursacht.

### Weitere Operatoren

JavaScript bietet zusätzlich die folgenden Operatoren:

#### Konditionaler Operator

```
<Bedingung> ? <Wert1> : <Wert2>
```

Wenn die Bedinung zum Wahrheitswert ```true``` evaluiert, wird Wert1 zurückgegeben, ansonsten Wert2.

Beispiel:

```JavaScript
  let isAtLeast18 = age >= 18 ? true : false;
```

#### Löschen von Objekteigenschaften

```
delete
```

Löschung von Eigenschaften aus Objekten, sowie Elementen aus Arrays.

#### Existenz einer Eigenschaft in einem Objekt

```
<eigenschaft> in <objekt>
```

#### Typüberprüfung

```
<objekt> instanceof <typ>
```

#### Typbestimmung

```
typeof<operand>
```
