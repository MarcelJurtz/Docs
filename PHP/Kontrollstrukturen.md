# Kontrollstrukturen

## If-Abfragen

```PHP
<?php
if(bedingung) {
  // Anweisungen
} elseif(bedingung) {
  // Anweisungen
} else {
  // Anweisungen
}
?>
```

## Switch-Case

```PHP
<?php
switch(ausdruck) {
  case(Wert1):
    // Anweisungen
    break;
  case(Wert2):
    // Anweisungen
    break;
  default:
    // Anweisungen
}
?>
```

Auch in PHP werden ohne *break* alle Anweisungen bis zum nächsten *break* durchgeführt.

## While-Loops

### Kopfgesteuert

```PHP
<?php
while(ausdruck) {
  // Anweisungen
}
?>
```

### Fußgesteuert

```PHP
<?php
do {
  // Anweisungen
} while(ausdruck);
?>
```

## For-Loops

```PHP
<?php
for($i = 0; $i <= 10; $i++) {
  // Anweisungen
}
?>
```

## Foreach-Loops

```PHP
<?php
foreach($array as $k => $v) {
  // Assoziatives Array mit Key $k und Value $v
  echo $v;
}
?>
```
