# Arrays

Für alle Datentypen können Arrays nach folgendem Muster angelegt werden:

```JavaScript
let array = [
  'Item 1',
  'Item 2',
  'Item 3'
];
```

In JavaScript können Arrays Variablen unterschiedlicher Typen enthalten.
Der Zugriff erfolgt wie gewohnt über den Index, begonnen bei 0.

```JavaScript
console.log(array[0]); // --> 'Item 1'
```

## Mehrdimensionale Arrays

Mehrdimensionale Arrays sind Arrays, die als Elemente weitere Arrays enthalten.

```JavaScript
let array = [
  [
    'Item 1',
    10,
    'Beschreibung 1'
  ],
  [
    'Item 2',
    3,
    'Beschreibung 2'
  ],
  [
    'Item 3',
    12,
    'Beschreibung 3'
  ],
];

// Zugriff, bsp. auf 'Beschreibung 2':
console.log(array[1][2]);
```
