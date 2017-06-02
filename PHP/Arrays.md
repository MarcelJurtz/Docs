# Arrays

Wie bei vielen Programmiersprachen (aber entgegengesetzt zu SQL, Achtung bei Datenbankinteraktionen) beginnen Array-Indizes mit 0.

Die Anzahl an Elementen eines Arrays erhält man mit ```sizeof($array)```, alternativ mit ```count($array)```.

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

Elemente zu einem assoziativen Array hinzufügen:

```PHP
$array = array();
$array[] = array($key => $value);
```

Arrays der gleichen Länge können folgendermaßen zu einem assoziativen Array verbunden werden:

```PHP
<?php
array_combine($keys, $values);
?>
```

## Arrays sortieren

* Aufsteigend: ```sort($array);```
* Absteigend: ```rsort($array);```
