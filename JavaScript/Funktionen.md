# Funktionen

```JavaScript
function bezeichnung(parameter) {
  // Anweisungen
}
```

## Funktionsausdrücke

Obige Schreibweise wird auch Funktionsdeklaration genannt. Alternativ können Funktionen als Funktionsausdrücke geschrieben werden. Hierbei wird häufig auf den Namen der Funktion verzichtet,
weshalb diese auch ```anonyme Funktionen``` genannt werden.

```JavaScript
let showMessage = function() {
  console.log("Hello World!");
}

showMessage();
```

Bei Funktionsausdrücken wird die Funktion also nicht über den Funktionsnamen aufgerufen, sondern über die Variable, der die Funktion zugewiesen wurde.
