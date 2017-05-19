# NodeJS

[Offizielle Website](https://nodejs.org/en/)

Mit NodeJS werden JavaScript-Dateien ausgeführt. Es ermöglicht die Ausführung von serverseitigem JavaScript.

## Hello World

Nach der Installation von Node kann es wie folgt verwendet werden:

Anlegen einer JavaScript-Datei.
```JavaScript
console.log("Hello World!");
```

Aufruf über Node (CMD):
```
node helloworld.js
```

## Module

[nodejs.org/api](https://nodejs.org/api/)

Node bietet diverse Module an, die eingebunden werden können, um verschiedene Funktionalitäten anzubieten. Oben stehender Link zeigt einer Übersicht dieser Module. Diese enthält auch passende Dokumentation und Beschreibungen.

### Einbinden eines Moduls:

```JavaScript
var http = require('http');
```

Require entspricht dem gleichnamigen Element unter php.

### HTTP-Server

Folgender Code erstellt einen einfachen HTTP-Server. Bei einer Anfrage wird durch den Callback die Methode "handleRequest" aufgerufen (http://localhost:3000), welche "Hello World!" in der Konsole ausgibt.

```JavaScript
var http = require('http');

function handleRequest(request, response) {
	console.log("Hello World!");
}

var server = http.createServer(handleRequest);
server.listen(3000);
```

Um die Rückgabe direkt zu beantworten kann folgender Code verwendet werden:

```JavaScript
function handleRequest(request, response) {
	response.write("Hello World!");
	response.end();
  // Alternativ: response.end("Hello World!");
}
```

Alternative Kurzschreibweise:
```JavaScript
var http = require('http');

http.createServer(function (request, response) {
	response.end("Hello World!");
}).listen(3000);
```

Genauere Informationen zu HTTP gibt's in der Dokumentation des Moduls auf oben verlinkter Website.
