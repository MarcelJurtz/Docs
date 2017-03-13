# Objekterstellung in JavaScript

## Zugriff auf Objekte

Zugriff auf Properties eines Objekts erfolgt mittels ```[]``` oder dem Namen des Properties.

Beispiel:

```JavaScript
var personObject = {
    firstName : "John",
    lastName : "Smith"
}
personObject.age = 23;
personObject["salary"] = 14000;

```

## State of JavaScript

Es gibt keinen *richtigen* Weg, in JavaScript Objekte zu erstellen. JavaScript ist nicht wie Python oder Java, JavaScript ist eine standardisierte Sprache, von verschiedenen Teilnehmern wird diskutiert, wie die Sprache funktionieren soll. Daraus entstehen Kompromisse und unterschiedliche Varianten, ein Ergebnis zu erzielen.

Zur Entwicklung ergibt sich hieraus der Bedarf, die Objekterstellung mit JavaScript zu erlernen,
und anschließend die beste Version für sich / das Unternehmen zu bestimmen.

## This & Bind

Beispielobjekt:

```JavaScript
// Objektliteral 'dog'
let dog = {
  // Eigenschaft
  sound: 'woof',
  // Methode
  talk: function() {
    console.log(this.sound);
  }
}

dog.talk(); // -> woof

// Soweit nichts allzu kompliziertes

let talkFunction = dog.talk;
talkFunction(); // -> undefined
```

JavaScript erlaubt die Zuweisung einer Funktion auf eine Variable. Dies ist möglich, da JavaScript nicht nur eine objektorientierte Programmiersprache ist, sondern auch eine funktionale Programmiersprache.

Im Kontext funktionaler Programmierung unterstützt JavaScript sogenannte *Higher-Order Functions*. Diese erlauben die oben gezeigte Schreibweise.

Die Ausgabe von *undefined* zeigt jedoch die objektorientierte Natur von JavaScript auf.
In funktionsorientierten Programmiersprachen existiert kein *this* bzw. *self*. Für objektorientierte Programmiersprachen sind diese jedoch essentiell.

Nach der Zuweisung ist ```talkFunction``` keine Methode (an Objekt angehängte Funktion) mehr, sondern eine einfache Funktion. ```this``` existiert nun nicht mehr im ursprünglich erdachten Sinn. Innerhalb einer Funktion referenziert *this* nicht auf den Kontext, in dem sie erzeugt wurde, sondern in dem sie aufgerufen wurde.

Mit ```bind``` kann jedoch dieser Kontext hergestellt werden.

```JavaScript

let talkFunction = dog.talk;
let boundFunction = talkFunction.bind(dog);
boundFunction(); // -> woof

```

Ein reaes Anwendungsbeispiel für diese Konstellation ist die Zuweisung einer Methode bei Unserinteraktion, beispielsweise mit einem Button.

```JavaScript

let button = document.getElementById("Button");
button.addEventListener(
  'click',
  dog.talk // this referenziert hier auf das window-Element

  // korrekte Lösung:
  dog.talk.bind(dog);
);

```

Nun können Funktionen erstellt werden, welche erst durch bind() einen Kontext erhalten.

Beispiel:
```JavaScript

function talk() {
  console.log(this.sound);
}

let max = {
  sound: 'Hello World!'
}

let maxTalk = talk.bind(max);

maxTalk(); // -> Hello World!

```

Eine alternative Schreibweise hierfür ist

```JavaScript

let talk = function() {
  console.log(this.sound);
}

let max = {
  speak: talk,
  sound: 'Hello World!'
}

max.speak(); // -> Hello World!

```

Diese funktioniert, da dem Objekt *max* die talk-Methode als Eigenschaft zugewiesen wurde.

Dieses Konzept kann zu Beginn recht kompliziert wirken, folgendes Beispiel verdeutlicht das jedoch:

```JavaScript

let talk = function() {
  console.log(this.sound);
}

let a = {
  speak: talk,
  sound: "Ich bin A"
}

let b = {
  blabla: a.speak,
  sound: "Ich bin B"
}

b.blabla();
// -> Ich bin B

```

talk() referenziert immer auf den aktuellen Kontext, der beim Aufruf der blabla()-Funktion b ist.

Funktionen in JavaScript sind kontextabhängig und können herumgereicht werden.
## Prototypen

Prototypen in JavaScript ermöglichen Vererbung.  
Prototypen und Klassen sind unterschiedliche Elemente.

Beispiel:

Ein Real-World-Beispiel einer Klasse ist ein Blueprint eines Gebäudes. Mit diesem Blueprint wird ein neues Gebäude gebaut.

Ein paralleles Beispiel für einen Prototypen wäre ein Delegierter, also eine Person, die eine Aufgabe auf Anweisung eines Anweisers ausführt.


```JavaScript
function talk(sound) {
  console.log(sound)
}

talk('Woof!');
// -> Woof!

// --------------
function talk() {
  console.log(this.sound)
}

talk();
// -> undefined

// --------------
function talk(sound) {
  console.log(this.sound)
}

let animal = {
  talk: talk
  // Bei Erstellen einer Eigenschaft mit dem gleichen Namen wie eine angebundene Funktion
  // kann folgende Schreibweise verwendet werden (ES6.0):
  // talk
}

let dog = {
  sound: 'Woof!'
}

dog.talk();
// -> cat.talk is not a function...
Object.setPrototypeOf(dog,animal);
dog.talk();
// -> Woof!
```

Beim Aufruf der talk()-Methode des Dog-Objekts sucht der Interpreter zuerst nach einer talk()-Eigenschaft im Dog-Objekt. Es wird keines gefunden, der Interpreter prüft anschließend, ob Dog einen Prototypen besitzt. Durch ```Object.setPrototypeOf(dog,animal);``` wird dieser im Objekt *animal* gefunden. Die Eigenschaft *talk* wird hier gefunden und aufgerufen. Der Aufruf der *this*-Eigenschaft in talk referenziert auf *Dog*. Der Prototyp entspricht also dem Eltern-Objekt.

Beispielhafte Vererbung: Obiger Code ergänzt um:

```JavaScript
let prarieDog = {
  howl: function() {
    console.log(this.sound.toUpperCase());
  }
}

prarieDog.howl();
// -> sound undefined
Object.setPrototypeOf(prarieDog,dog);
prarieDog.howl();
// -> WOOF!
```

Prototypen sind Delegates, sie erstellen keine Kopie der geerbten Eigenschaften, sondern deligieren lediglich Aufgaben an die Parent-Objekte.

Wenn beispielsweise nach dem Zuweisen eines Prototypen die talk()-Funktion geändert wird,
wird die geänderte Version aufgerufen, wenn der Zugriff nach der Änderung stattfindet.


### Fazit

Wenn eine Eigenschaft innerhalb eines Objekts nicht gefunden wird, wird dessen Prototyp durchsucht. Hierdurch lässt sich eine Hierarchie aufbauen.


## New

Erstellen von Objekten mit JavaScript. In diesem Kontext wird *new* auf Funktionen bezogen, nicht in Verbindung mit dem Keyword *Class*.

```JavaScript
function Person(saying) {
  this.saying = saying;
}

Person.prototype.talk = function() {
  console.log('I say ' + this.saying);
}

var max = new Person('Hello World!');
max.talk();
// I say Hello World!
```

Was passiert beim Aufruf von ```new```?

1. Erstellen eines neuen, leeren Objekts.
2. Ermitteln des Namens der Funktion, Check des Prototypen des Objekts und setzen des Prototyps des neuen Objekts auf diesen.
3. Ermitteln der Funktion und zuweisen als Instanz sowie Ausführen des Konstruktors
4. Rückgabe des Objekts

Das Class-Keyword folgt intern dem gleiche Prinzip.

Mit diesen Grundlagen kann die Funktionalität von *new* in einer eigenen Funktion angewendet werden.

```JavaScript

function newDemo(constructor, ) {
  // 1.
  var obj = {};

  // 2.
  Object.setPrototypeOf(obj, constructor.prototype);

  // 3.
  // arguments enthält alle übergebenen Elemente
  // ES 5
  var argsArray = Array.prototype.slice.apply(arguments);
  // ES 6
  var argsArray = Array.from(arguments);
  constructor.apply(obj,argsArray.slice(1));
  // apply = bind mit sofortiger Ausführung

  // 4.
  return obj;
}

var max = newDemo(Person, 'Hello World!');
max.talk();

```

## Object.create

Erstellt ein Objekt mit einem auf ein bestimmtes Objekt festgelegtem Prototypen.

```JavaScript

const dog = {
  makeSound: function() {
    console.log("Woof!");
  }
}

dog.makeSound(); // -> Woof!

// Neue Schreibweise:

const dog = {
  makeSound: function() {
    console.log(this.sound);
  }
}

const max = Object.create(dog);
max.sound = "Woof!";
max.makeSound(); // -> Woof!

```

Es wird also ein neues Objekt *max* erstellt, dessen Prototyp auf *dog* gesetzt wird.
Die Abfrage  ```dog.isPrototypeOf(max)``` gibt nun *true* zurück.

Max ist keine Kopie von dog, sondern ein neues Objekt mit einer Refernz zu dog.
Wird eine Eigenschaft von max aufgerufen, die dieser nicht besitzt, so wird der Aufruf an den
Prototypen delegiert.

Dieses Beispiel lässt sich jedoch auch mit *new* umsetzen, warum existiert ```Object.create()``` dann überhaupt?

Create ist natürlicher gegenüber dem Prototyp-Modell als *new*.

Bisher wurde *new* in Verbindung mit Funktionen verwendet, um etwas zu gestalten, das wie eine Klasse aussieht. Diese Vorgehensweise war lange Zeit der defacto-Weg hierzu.

Jedoch war diese Schreibweise etwas seltsam und unübersichtlich, weshalb Object.Create geschrieben wurde.

Um den Prozess besser verstehen zu können, wird mit folgendem Code die Create-Methode implementiert:

```JavaScript

function objectCreate(proto) {
  const obj = {};
  Object.setPrototypeOf(obj,proto);
  return obj;
}

```

Die manuelle Methode sollte aber aufgrund von Performance nicht verwendet werden.
Ein Beispiel zur Umsetzung einer Objekterstellung inklusive Parametern kann wie folgt aussehen:

```JavaScript

const dog = {
  init: function(sound) {
    this.sound = sound;
    return this;
  }
  makeSound: function() {
    console.log(this.sound);
  }
}

const max = Object.create(dog).init("Woof!");
max.makeSound(); // -> Woof!
```

Object.creae ist eine sehr performante Art, um Objekte zu erzeugen.
