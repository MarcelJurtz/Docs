# Schleifen

Nutzung von Schleifen zur Iteration durch Listen.

```Python
names = ['Peter','Paul','Marc','Eric']
for name in names:
  print(name)

print("End of Loop!")
```

Steuerung von Schleifen anhand der Einrückung.

Zahlenbasierte Schleifendurchläufe:

```Python
for value in range(1,5):
  print(str(value))
```

Durchlaufen der Schleife und Ausgabe der Werte 1,2,3,4.
5 wird nicht ausgegeben, da durch die Definition im Schleifenkopf festgelegt wird, dass die Schleife bei 1 beginnt und bei 5 aufhört.  
Da bei 5 aufgehört wird, wird dieser Wert nicht mehr ausgegeben.

Solche numerischen Listen können auch Leicht erzeugt / gespeichert werden:

```Python
numbers = list(range(1,4)) # [1,2,3]
numbers = list(range(2,12,2)) # [2,4,6,8,10]
numbers = list(range(0,12,3)) # [0,3,6,9]  
```

Alternatives Verwendungsbeispiel:

```Python
squares = []
for num in range(1,11):
  squares.append(num ** 2)

print(squares)

# Alternativschreibweise:
squares = [value ** 2 for value in range(1,11)]
print(squares)
```

Die Iteration durch Listen kann mittels Slicing eingeschränkt werden:

```Python
for name in names[:2]:
  print(name)
```
