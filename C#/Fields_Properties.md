# Fields & Properties

Getter und Setter sind üblicherweise Methoden zum Setzen von privaten Membervariablen.

Oft findet sich aber auch folgende Schreibweise:

```CSharp
// 1
Public string name { get; set; }
```

Der Unterschied zur Verwendung von

```CSharp
// 2
Public string name;
```

besteht darin, dass Schreibweise 1 Properties anstelle von Fields (Variablen, die direkt in einer Klasse deklariert werden), verwendet werden.

Ein Property kapselt also ein Field. Soll nachträglich beispielsweise Datenvalidation eingefügt werden, kann dies direkt in die Setter-Methode eines Properties eingefügt werden. Im Falle der Verwendung von Fields ist das nicht so ohne Weiteres möglich. Dort müsste dann jeder Zugriff wie folgt abgeändert werden:

```CSharp
// Früher
elem.value = 10;

// Jetzt
elem.setValue(10);
```

Ein praktischer Vorteil der ganz oben genannten automatisch implementierten Properties liegt darin, dass Breakpoints auf die Getter und Setter gesetzt werden können, da diese richtige Methoden sind. Auf ein Field direkt kann dagegen kein Breakpoint gesetzt werden.

Außerdem kann der *set*-Teil weggelassen werden, sodass ein readonly-Property entsteht.
