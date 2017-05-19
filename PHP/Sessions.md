# Sessionverwaltung

Starten der Session ist in jedem PHP-Dokument erforderlich,
in dem auf Session-Elemente zugegriffen werden soll:

```PHP
<?php
session_start();
?>
```

Entgegengesetzt zu Cookies werden Sessionvariablen serverseitig gespeichert.

## Verwenden von Sessionvariablen

```PHP
<?php
$_SESSION['varName'] = "varValue";
?>
```

Bezeichnungen der Sessionvariablen werden vom Entwickler festgelegt.

Speichern von Arrays ist ebenfalls möglich:

```PHP
<?php
$_SESSION['arrayName'][] = array('a','b','c');
?>
```

Die Session-Variable ist also ein zuvor beschriebenes assoziatives Array,
und kann entsprechend verwendet werden.

## Sessions beenden

In der Standard-PHP-Konfiguration verwenden Sessions ein Timeout von 1440 Sekunden, also 24 Minuten. Alternativ kann Sessioninhalt (beispielsweise bei Logout) wie folgt gelöscht werden:

```PHP
<?php
// Beispielhafter Logout-Vorgang

// Start der Session
session_start();

// Beenden der Session
session_destroy();

// Umleitung zur Startseite
header('Location: index.php');

// Alternativ: Beenden des PHP-Programms
exit();
?>
```
