# Schleifen

Unter JavaScript stehen die allgemein bekannten Schleifentypen zur Verfügung:
* for
* while
* do-while

Bei geschachtelten Schleifen sind per Konvention maximal drei Ebenen zu verwenden.
Für die Zählervariablen haben sich Bezeichnungen nach dem Muster i,j,k,... durchgesetzt.

## Schleifen vorzeitig abbrechen

Mit dem Keyword ```break``` wird eine Schleife vor Beenden aller Iterationen abgebrochen.
Um nur die Ausführung der aktuellen Iteration abzubrechen wird das Keyword ```continue``` verwendet.

Bei geschachtelten Schleifen wird durch Continue die Iteration der Schleife übersprungen, in der auch das Keyword auftaucht. Um bei einem Continue in der inneren Schleife aber auch die äußere Iteration abzubrechen, existieren sogenannte Sprungmarken.

## Sprungmarken

Auch: Labels.

Beispiel:

```JavaScript
let numbers = [2, 4, 56, 22, 65, 2, 54, 88, 29];
outerloop:
  for(let i = 0; i < numbers.length; i++) {
    let number = numbers[i];
    innerloop:
      for(let j = i + 1; j < numbers.length; j++) {
        let number2 = numbers[j];
        console.log("Vergleiche " + number + " mit " + number2);
        if(number === number2) {
          console.log("Gleiche Zahlen gefunden!");
          continue outerloop;
        }
      }
  }
```

Sobald zwei gleiche Zahlen hier gefunden wurden, wird die Iteration für das Element an Stelle i gestoppt.

Sprungmarken werden in der Praxis recht selten verwendet,
da der Code schnell unübersichtlich wird.
