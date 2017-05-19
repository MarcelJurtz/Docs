# Joins

Mit Joins werden Tabellen anhand festgelegter Spalten verbunden. Hierdurch wird ermöglicht, Tabellen entsprechend dem relationalen Datenbankmodell aufzubauen.


Tabelle: bands

| Band                    | ID  |
|-------------------------|-----|
| Linkin Park             | 0   |
| Disturbed               | 1   |
| Five Finger Death Punch | 2   |

Tabelle: alben

| Album                   | Band  |
|-------------------------|-------|
| Hybrid Theory           | 0     |
| Immortalized            | 1     |
| Got your Six            | 2     |
| American Capitalist     | 2     |
| A thousand Suns         | 0     |

Bands sind hier mit IDs versehen. Wenn herausgefunden werden will, welche Band welches Album gehört,
müssen die Tabellen über die ID-Spalten verknüpft werden.

## INNER JOIN

```SQL
SELECT Band, Album
FROM bands b
INNER JOIN alben a ON a.Band=b.ID;
```

| Band                    | Album               |
|-------------------------|---------------------|
| Linkin Park             | Hybrid Theory       |
| Linkin Park             | A thousand Suns     |
| Disturbed               | Immortalized        |
| Five Finger Death Punch | American Capitalist |
| Five Finger Death Punch | Got your Six        |

Das Schema von Innerjoins ist also folgendes:

```SQL
SELECT col, [..]
FROM tab1
INNER JOIN tab2 ON tab1.col_name = tab2.col_name;
```

## LEFT JOIN

(LEFT OUTER JOIN)

Im obigen Beispiel sind im Ergebnis alle Elemente erhalten,
denen ein Eintrag auf beiden Seiten des Joins zuordbar ist.

Beim LEFT (OUTER) JOIN werden alle Elemente der linken Tabelle (tab1) im Ergebnis verwendet,
auch wenn diese keinen Partner in der zweiten Tabelle (tab2) besitzen.

```SQL
SELECT col, [..]
FROM tab1
LEFT JOIN tab2 ON tab1.col_name = tab2.col_name;
```

## RIGHT JOIN

(RIGHT OUTER JOIN)

Der RIGHT (OUTER) JOIN funktioniert analog dem oben genannten LEFT JOIN.

## FULL JOIN

Der FULL JOIN entspricht einer Kombination des LEFT und RIGHT JOINS,
Elemente ohne Partner werden beidseitig zugelassen.

Elemente ohne Partner erhalten zwar die gejointen Spalten, diese bleiben jedoch leer (null).

## SELF JOIN

Ein SELF JOIN bezeichnet den JOIN einer Tabelle mit sich selbst. Dies ist beispielsweise hilfreich,
um Mitarbeiter zu suchen, die in einem Ort arbeiten, in dem sie gleichzeitig auch leben.
