# Datenbankzugriff

Verwendung meistens von MySQL.

MySQL-Funktionalitäten werden durch ```mysql```-Funktionen implementiert,
jedoch sollten die ```mysqli```-Funktionen (MySQL-Improved) verwendet werden, da diese die ursprünglichen Funktionen abgelöst haben.

## Verbindungsaufbau

```PHP
<?php
// Aufbau einer Verbindung
// Angabe einer Datenbank ist optional
$connection = mysqli_connect(Adresse, Username, Passwort, Datenbank);

// Schließen der Verbindung
mysqli_close($connection);
?>
```

Die Kommunikation mit der Datenbank setzt selbstverständlich eine aktive Verbindung voraus.

## Ausführen von SQL-Queries

```PHP
<?php
$rows = mysqli_query($connection, $sqlQuery);
?>
```

## Lesen von Datensätzen


```PHP
<?php
// Iteration durch Ergebnisse
while($entry = mysqli_fetch_assoc($row))
{
  echo $entry['colName'];
}
?>
```

## Verhindern von SQL-Injection

$string = mysqli_real_escape_string($connection, $unescapedString);
