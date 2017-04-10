# Variablen

Variablen werden unter PHP mit einem Dollar-Zeichen eingeleitet.  
Wie beispielsweise bei JavaScript verwendet PHP keine Typisierung,
der Datentyp kann im Lauf des Programms geändert werden.

## Variablendeklaration

```PHP
$name = "Marcel";
$currentAge = 20;
$coding = true;
```

Zeichenketten können sowohl in doppelten (") als auch einfachen (')
Anführungszeichen angegeben werden.
Im Falle der Nutzung der doppelten können Werte von Variablen direkt in die Zeichenketten eingebunden werden, Stringkonkatenation ist aber mit einem Punkt (.) möglich.

```PHP
$w = "world";
echo "Hello $w";

// Alternativ:
echo 'Hello ' . $w;
```

## Superglobale Variablen

PHP bietet sogenannte superglobalen Variablen an, hier handelt es sich um Variablen, die dem Entwickler zur Verfügung gestellt werden, und beispielsweise den Zugriff auf Eingabefelder des aufrufenden Formulars erlauben:

```PHP
// Zugriff auf Formularwerte (POST)
$username = $_POST['username'];

// Zugriff auf Formularwerte (GET)
$username = $_GET['username'];

// Sessionvariablen (frei definierbar)
$_SESSION['username'] = $username;
```

## Konstanten

```PHP
define("CONSTANT_NAME","Hello World!");
echo CONSTANT_NAME;
```
