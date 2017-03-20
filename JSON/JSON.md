# JSON

JSON ist ein einfaches Format zum Austausch von Daten.

Unter JSON existieren keine Kommentare,
die meisten Parser akzeptieren jedoch ```//``` bzw ```/* */```.

Folgendes JSON-Objekt erklärt den Aufbau:

```JSON
{
  "Schlüssel": "Wert",
  "Zeichenkette": "Inhalt",
  "Zahl": 0,
  "Wahrheitswert": false,
  "Null": null,
  "Große Zahl": 1.3e+100,
  "Array": [
    0,
    1,
    "Hans-Peter",
    true
  ],
  "Objekt": {
    "Schachtelobjekt": {
      "Text": "Hallo Welt"
    }
  },
}
```

Bei JSON spielt Formatierung keine Rolle. Das Komma zur Trennung kann beispielsweise auch in der Folgezeile stehen. Die Einrückung spielt keine Rolle, es können beliebig viele Tabs und Spaces platziert werden.
