# SQL Grundlagen

Structured Query Language

## Allgemeine Syntax

```SQL
SELECT (Spaltenauswahl) FROM (Tabellenname);
```

Spalten anhand deren Namen angeben, getrennt durch Komma.  
Auswahl aller Spalten mit * möglich.

SQL-Keywords sind nicht case-sensitiv.

## SELECT DISTINCT

Wird nach ```SELECT``` zusätzlich das Keyword ```DISTINCT``` angegeben, so werden in der Ergebnismenge vorkommende Duplikate entfernt und nur ein Repräsentant ausgegeben.
Dies ist hilfreich, um zu ermitteln, wieviele unterschiedliche Werte in bestimmten Spalten stehen.

## Bedingungen / WHERE

Eingrenzung der Ergebnismenge durch Filterung von Attributwerten.

```SQL
SELECT * FROM DEMO_TABLE WHERE name='Meyer';
```

### Operatoren


| Operator     | Funktion                                                                          |
|--------------|-----------------------------------------------------------------------------------|
| =            | Gleicheit                                                                         |
| <> bzw. !=   | Ungleichheit                                                                      |
| >            | 	Größer                                                                           |
| >=           |  Größergleich                                                                     |
| <            | 	Kleiner                                                                          |
| <=           |  Kleinergleich                                                                    |
| BETWEEN      | 	Innerhalb eines vorgegebenen Bereichs                                            |
| LIKE         | 	Muster, beispielsweise wenn der Wert nur teilweise bekannt ist                   |
| IN           | 	Mehrere Möglichkeiten (Entspricht OR-Verknüpfung von mehreren Gleicheitsangaben) |

Die Verwendung von BETWEEN sieht dabei folgendermaßen aus:

```SQL
[...] WHERE price BETWEEN 5 AND 10;
```

### AND, OR, NOT

Verknüpfung von Operatoren.

```SQL
SELECT * FROM DEMO_TABLE WHERE col1="A" AND col2="B";
SELECT * FROM DEMO_TABLE WHERE col1="A" OR col2="B";
SELECT * FROM DEMO_TABLE WHERE NOT col1="A";
```

* UND-Verknüpfung: AND
* ODER-Verknüpfung: OR
* Negation: NOT

Die verschiedenen Keywords können auch kombiniert werden:

```SQL
SELECT * FROM DEMO_TABLE WHERE col1="A" AND ( col2="B" OR col3="C") AND NOT col4="D";
```

## Sortierung

Ab- bzw. aufsteigende Sortierung mit ```ORDER BY``` sowie ```ASC``` (Standard) bzw. ```DESC```

```SQL
SELECT * FROM DEMO_TABLE ORDER BY col3;
SELECT * FROM DEMO_TABLE ORDER BY col3 ASC;
SELECT * FROM DEMO_TABLE ORDER BY col3 DESC;
```

## NULL

Abfrage von NULL-Werten:

```SQL
... WHERE col IS NULL;
... WHERE col IS NOT NULL;
```

## Alias

Mithilfe eines Alias können Spalten intern umbenannt werden, um Anfragen übersichtlicher zu gestalten.

```SQL
SELECT col1 AS username, col2, col3 FROM DEMO_TABLE WHERE username IN('A','B','C');
```
