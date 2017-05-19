# Arrays

Wie bei vielen Programmiersprachen (aber entgegengesetzt zu SQL, Achtung bei Datenbankinteraktionen) beginnen Array-Indizes mit 0.

Die Anzahl an Elementen eines Arrays erhält man mit ```sizeof($array)```

## Erzeugen von Arrays

```PHP
<?php
$array = array("Orwell", "Huxley", "Hemingway");
echo $array[1]; // Huxley
?>
```

## Anhängen von Elementen

```PHP
<?php
$array[] = "Austen";
?>
```

## Assoziative Arrays

Assoziative Arrays erlauben den Zugriff auf Array-Elemente anhand eines Schlüssels.

```PHP
<?php
$authors = array(
  "A1" => "Orwell",
  "A2" => "Huxley",
  "A3" => "Hemingway"
);

echo $authors["A2"]; // Huxley
?>
```

## Arrays sortieren

* Aufsteigend: ```sort($array);```
* Absteigend: ```rsort($array);```
