# Funktionen

PHP unterscheidet zwischen benutzerdefinierten (eigenen) Funktionen, sowie Standardfunktionen, welche durch die Programmiersprache festgelegt sind.

## Standardfunktionen

* ```echo();```
* ```gettype($var);```
* ```settype($var, typ);```
* ```isset($var);```
* ```md5($string);```
* ```htmlentities($var);```
* Div. Mathematische Funktionen

## Benutzerdefinierte Funktionen

```PHP
<?php
function funktion() {
  // Anweisungen
}

// Parameter
function funktion_1($param1) {
  // Anweisungen
}

// Standardwerte für Parameter
function funktion_2($param1, $param2=42) {
  // Anweisungen
}

// Aufruf
funktion();
?>
```

Funktionen können in andere Dateien ausgelagert werden. Hier gilt die Namenskonvention *name.inc.php*. Der Aufruf erfolgt anschließend mit einer Zeile (zu Beginn der PHP-Datei): ```include "name.inc.php";```
