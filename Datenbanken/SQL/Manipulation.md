# SQL - Manipulation

## INSERT

Mit ```INSERT INTO``` werden neue Datensätze in die Tabelle eingefügt.

```SQL
INSERT INTO DEMO_TABLE (col1, col2, ...) VALUES (val1, val2, ...);
```

Die Angabe der Spalten ist optional, wenn alle Spalten befüllt werden, sowie die Wertreihenfolge mit der Datenbank übereinstimmt.

## UPDATE

Mit ```UPDATE``` werden bestehende Datensätze geändert.

```SQL
UPDATE DEMO_TABLE
SET col1 = val1, col2 = val2, ...
WHERE bedingung;
```

Bei Weglassen des WHERE-Teils werden alle Datensätze der Tabelle geändert.

## DELETE

Mit ```DELETE FROM``` werden Datensätze gelöscht.

```SQL
DELETE FROM DEMO_TABLE WHERE bedingung;
```

Bei Weglassen des WHERE-Teils werden alle Datensätze der Tabelle gelöscht.
