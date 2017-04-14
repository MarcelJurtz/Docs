# Listen

Arrays unter Python werden Listen genannt.

## Anlegen von Listen

```Python
# Anlegen einer Liste
languages = ['english','german','latin']
# Anlegen einer leeren Liste
emptyList = []

print(languages) # ['english','german','latin']
```

## Zugriff auf Einträge von Listen

```Python
# Indexbasierter Zugriff
print(languages[1]) # german
# Rückwärtszählen
print(languages[-1]) # latin
print(languages[-2]) # german
```

## Hinzufügen von Einträgen

```Python
# Elemente nachträglich hinzufügen
languages.append('italian')
print(languages) # ['english','german','latin', 'italian']

# Element an bestimmter Stelle einfügen
languages.insert(1, 'japanese')
print(languages) # ['english','japanese','german','latin', 'italian']
```

## Entfernen von Einträgen

```Python
# Element per Index aus Liste entfernen
del(languages[3]) # Entfernt 'latin'

# Entfernen des letzten Elements mit Erhaltung der Verwendung
lastLanguage = languages.pop()
print(lastLanguage) # italian

# Pop an bestimmter Stelle:
secondLanguage = languages.pop(1)
print(secondLanguage) # japanese

# Element anhand des Wertes entfernen
languages.remove('german')
# Entfernt lediglich das erste Auftreten
```

## Listen sortieren

```Python
characters = ['A','a','b','c','C','D']

# Temporäre Sortierung
print(sorted(characters)) # ['A', 'C', 'D', 'a', 'b', 'c']

# Liste invertieren
characters.reverse()

# Dauerhafte Sortierung
characters.sort()

# Invertierte Sortierung
characters.sort(reverse=True)
# Parameter auch bei sorted() möglich
```

## Länge einer Liste ermitteln

```Python
len(arrayName)
```

## Einfache Statistik-Informationen

```Python
min(arrayName)
max(arrayName)
sum(arrayName)
```

## Slicing

Mittels Slicing kann nur eine Teil einer Liste verwendet werden.

```Python
names = ['Max','Peter','Steve','Cesar']
print(names) # ['Max','Peter','Steve','Cesar']
print(names[0:-2]) # ['Max','Peter']
print(names[:-2]) # ['Max','Peter']
# 0 als erster Wert kann weggelassen werden
print(names[1,3]) # ['Peter', 'Steve']
```

## Listen kopieren

```Python
list1 = [1,2,3,4,5]
list2 = list1
```

funktioniert nicht, da hier eine Referenz von list2 auf list1 gesetzt wird, Änderungen an einem der beiden Listen sind somit auch in der anderen Liste ersichtlich.

Bessere Alternative:
```Python
list2 = list1[:]
```

Die Zuweisung erfolgt wie beim Slicing, durch Angabe eines Doppelpunkts wird die gesamte Liste kopiert, Einschränkungen sind wie oben dargestellt möglich.
