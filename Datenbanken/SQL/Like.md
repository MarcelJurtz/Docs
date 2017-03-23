# LIKE

Der LIKE-Operator wird in WHERE-Bedingungen verwendet,
um Spalten nach einem bestimmten Muster zu filtern.

Der LIKE-Operator wird mit zwei Zeichen verwendet,
welche in abzufragende Zeichenketten eingesetzt werden können.

* % - Das Prozentzeichen repräsentiert kein, ein oder mehrere Zeichen
* _ - Der Unterstrich repräsentiert genau ein Zeichen

```SQL
// Selektion aller Werte, die mit 'e' anfangen
[..] WHERE col1 LIKE 'e%'

// Selektion aller Werte, die mit 'e' enden
[..] WHERE col1 LIKE '%e'

// Selektion aller Werte, die 'er' enthalten
[..] WHERE col1 LIKE '%er%'

// Selektion aller Werte, die ein 'o' an zweiter Stelle besitzen
[..] WHERE col1 LIKE '_o%'

// Selektion aller Werte, die mit 'M' anfangen und mit 'er' enden
[..] WHERE col1 LIKE 'M%er'
```
