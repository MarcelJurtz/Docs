# Objekte

## Literal-Schreibweise

Die Literal-Schreibweise verwendet geschweifte Klammern ```{}``` zur Kennzeichnung von Objekten.
  ```JavaScript
let user = {
  name: 'Max Mustermann',
  birthday: '01.01.1970',
  greet: function() {
    console.log("Hallo " + this.name);
  }
}
```

Das Objekt besitzt die Eigenschaften ```name``` und ```birthday```
sowie die Methode ```greet()```.

Prinzipiell sind Objekte also Key-Value-Paare, getrennt durch ```:``` und erweitert durch ```,```.

Das Keyword ```this``` referenziert das ```name```-Attribut des aktuellen Objekts.
