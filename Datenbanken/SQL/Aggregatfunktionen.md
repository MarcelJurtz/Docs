# Aggregatfunktionen

## MIN

Selektiert kleinsten Wert einer Spalte.

```SQL
SELECT MIN(col1) FROM DEMO_TABLE WHERE bedingung.
```

## MAX

Selektiert größten Wert einer Spalte.

```SQL
SELECT MAX(col1) FROM DEMO_TABLE WHERE bedingung.
```

## COUNT

Gibt die Anzahl passender Datensätze zurück.

```SQL
SELECT COUNT(*) FROM DEMO_TABLE WHERE col1="A";
```

## AVG

Ermittelt das arithmetische Mittel einer Spalte.

```SQL
SELECT AVG(price) FROM product_db WHERE status="available";
```

## SUM

Ermittelt die Summe der Werte einer Spalte.

```SQL
SELECT SUM(price) FROM product_db WHERE status="sold";
```
