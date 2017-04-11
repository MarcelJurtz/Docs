# Klassen

```PHP
<?php
class eineKlasse {
  private $text = "Hello World!";
  private $x;

  public function __construct($val) {
    $this->ChangeText($val);
  }

  public function ChangeText($text) {
    $this->text = $text;
  }

  public function __destruct() {
    echo "Instanz zerstört";
  }
}

$instanz = new eineKlasse("Hallo");
$instanz->ChangeText("Welt");
$instanz = null; // "Instanz zerstört"
?>
```

## Vererbung

```PHP
<?php
class neueKlasse extends eineKlasse {
  // ...
}
?>
```

Die Klasse erbt Eigenschaften und Methoden inklusive Konstruktor und Destruktor.

Explizites Aufrufen des Konstruktors der Oberklasse:

```PHP
<?php
parent::__construct(Params);
?>
```
