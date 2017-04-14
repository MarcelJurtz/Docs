# Variablen

## Variablendeklaration

```python
message = "Hello World!"
```

Keine Typisierung!

## Strings

### Stringmanipulation

Bearbeitung von Zeichenketten mittels verschiedener Standardmethoden

```Python
string = "Hello world!"
str2 = string.lower(); # hello world!
str2 = string.upper(); # HELLO WORLD!
str2 = string.title(); # Hello World!

# Bearbeiten von Leerzeichen
string = "     hello   "
str2 = string.lstrip() # "hello   "
str2 = string.rstrip() # "     hello"
str2 = string.strip() # "hello"
```

### Stringkonkatenation

```Python
string1 = "Hello"
string2 = "World"
print(string1 + " " + string2 + "!")
```

## Zahlen

Rechenoperatoren:
* +
* -
* *
* /
* %
* \**
* //

Achtung! Python2:
```Python
print(str(3/2)) # 1
print(str(3.0/2)) # 1.5
print(str(3/2.0)) # 1.5
print(str(3.0/2.0)) # 1.5
```

### Verwendung von Zahlen in Zeichenketten

Um in Python Zahlen in Zeichenketten verwenden zu können, müssen diese explizit konvertiert werden:

```Python
age = 20
print("I am " + str(age) + " years old!");
```
