# TypeScript

TypeScript ist eine Ergänzung von JavaScript um Typisierung,
die durch Microsoft ins Leben gerufen wurde.

Der TypeScript-Compiler erstellt aus den .ts-Dateien dann .js-Dateien.

Den Compiler kann man aus den folgenden Quellen erhalten:
* Nuget
* npm

TypeScript kann mit Visual Studio entwickelt werden, was einige hilfreiche Features hierzu anbietet,
beispielsweise wird beim Drag and Drop einer TypeScript-Datei in eine HTML-Seite automatisch ein Verweis auf die JavaScript-Datei angelegt.

Bei Verwendung eines *einfacheren* Editors als Visual Studio, beispielsweise Visual Studio Code,
muss der Compiler über die Kommandozeile verwendet werden.

Folgender Code sorgt dafür, dass die .ts-Dateien immer beim Speichern übersetzt werden:

```bash

tsc datei1.ts datei2.ts --watch --target es5 --module amd

```

* ```tsc``` TypeScript-Compiler
* ```watch``` Automatische Übersetzung, nur verfügbare, wenn Bezug aus Node-Paketen (VS erledigt das aber auch)
* ```target es5``` Zielvesion (ECMAScript 5)
* ```module amd``` Modulformat AMD

TypeScript stellt eine Obermenge von JavaScript dar, d.h. jede JavaScript-Datei ist auch gültiger TypeScript-Code

## Syntax

TypeScript ist wie bereits erwähnt JavaScript mit Typisierung. Der Datentyp wird mit Doppelpunkt vom Variablennamen getrennt:

```JavaScript

var text:string = "Hello World!";

```

Die Verfügbaren Datentypen sind die folgenden:

* number
* boolean
* string

Diese drei werden auch als *primitive Datentypen* bezeichnet.
Außerdem steht der Typ *any* zur Verfügung.  
Dieser kann beliebige Werte enthalten und entspricht dem Standardverhalten von JavaScript.

Auch wenn bei der Deklaration kein Typ angegeben wurde, wird die Variable bei der Initialisierung mit diesem Datentypen geprägt. Es ist also keine Konvertierung möglich.

```JavaScript

var text = "Hello World";
text = 123; // Falsch!

```

Wenn die Deklaration keine Initialisierung enthält, wird der Datentyp *any* gesetzt.

### Arrays

Arrays werden zum Beispiel mit eigenen Typen realisiert:

```JavaScript

type arr = number[];
var numbers:arr;

// Alternativ:
var numbers: Array<number>;

// Nutzung:
numbers = [1,2,54,7,21,18];

for(let num of numbers) {
  console.log(num);
}

```

### Klassen

## Asynchrones TypeScript

## Node mit TypeScript: Node.ts
