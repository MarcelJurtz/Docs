# Bash

Bash ist der Name einer UNIX-Shell.  
Bash-Skripte werden der Einfachheit halber als .sh-Dateien gespeichert.  
Bash funktioniert im Kontext eines aktuellen Verzeichnisses,
Befehle wie ```ls``` können also in Skripten verwendet werden.

## Allgemeine Befehle

* ```clear``` Leert das Terminalfenster
* ```cd``` Verzeichniswechsel
* ```ls``` Listet Dateien und Verzeichnisse
* ```man``` Zeigt Beschreibungen zu Befehlen an
* ```cat``` Ausgabe von Dateiinhalten in STDOUT
* ```cp``` Kopieren von Dateien
* ```mv``` Verschieben von Dateien (-> in gleichem Verzeichnis -> Umbennenung)
* ```mkdir``` Verzeichnis erstellen
* ```wc``` Wordcount
* ```rm``` Dateien / Verzeichnisse löschen
* ```tail``` Ausgabe der letzten Zeilen einer Datei
* ```head``` Ausgabe der ersten Zeilen einer Datei
* ```sort``` Zeilen einer Datei sortieren

## Shebang

```Bash
#!/bin/bash
# Die erste Zeile eines Bash-Skripts enthält den 'Shebang'
# Dieser weist das System an, wie das Skript ausgeführt werden muss
```

## Kommentare

```Bash
# Kommentare werden mit einer # eingeleitet
```

## Textausgabe

```Bash
echo "Hello World!"
echo "Neue Zeile"
# Trennung von Kommandos mit einer neuen Zeile oder einem Semikolon
echo "Hello World!";echo "Neue Zeile"
```

## Variablendeklaration

```Bash
variable="Hello World!"
echo variable     # variable
echo $variable    # Hello World
echo "$variable"  # Hello World
echo '$variable'  # $variable
```

## Parameter Expansion

```Bash
# Parameter Expansion ${ }:
echo ${variable}
# Bezug des Werts einer Variablen.
# Der Wert wird "erweitert" oder ausgegeben.
# Während der Erweiterungszeit kann dieser modifiziert werden.
```

### String Replacement

```Bash
variable="The weather is fine!"
echo ${variable/fine/bad} # The weather is bad!
```

### Substrings

```Bash
variable="Hello World"
length=5
echo ${variable:0:length} # Hello
```

### Default-Werte

```Bash
echo ${name:-"Max Mustermann"}
# Max Mustermann, wenn name = null oder leerer String
# Nur Rückgabe des Wertes, keine Änderung der Variablen
```

## Brace Expansion

Ausgabe von Wert Reihen

```Bash
echo {1..100} # 1 2 3 ... 100
echo {A..Z} # A B C ... Z
```

## Vordefinierte Variablen

Folgende Liste ist lediglich ein Ausschnitt der verfügbaren Variablen.

```Bash
echo "Rückgabewert des zuletzt aktiven Programms: $?"
echo "Rückgabewert des aktuellen Programms: $0"
echo "PID des Skripts: $$"
echo "Anzahl an an Skript übergebener Parameter $#"
echo "Argumente, die an das Skript übergeben wurden: $@"
echo "Argumente des Skripts, aufgeteilt in verschiedene Variablen $1 $2..."
```

## Befehle in Variablen

Um das aktuelle Verzeichnis auszugeben, gibt es den Befehl ```pwd```.
Um diesen in einer Zeichenkette zu kapseln, gibt es zwei Möglichkeiten:

* Ausführen des Befehls
* Verwendung der globalen Variablen

```Bash
echo "PWD: $(pwd)" # Führt 'pwd' aus und speichert den Output
echo "PWD: $PWD" # Bezieht den Wert aus der Variablen
```

## Eingaben einlesen

```Bash
echo "Who are you?"
read Name
echo Hello, $Name!
```

## Redirection

Ein- und Ausgaben können von STDIN bzw. STDOUT (und STDERR) umgeleitet werden.

```Bash
statement < input.txt   # Beziehe Input aus Datei
statement > output.txt  # Schreibe Output in Datei
statement 2> error.txt  # Schreibe Errorlog in Datei
```

Beim Schreiben mit ```>``` wird die Dateiersetzt, falls sie existiert.
Um stattdessen Text anzuhängen, wird ```>>``` verwendet.

Alternativ kann zur Umleitung von Befehlen die Pipe ```|``` verwendet werden.
Der Output des vorhergehenden Befehls wird als Input für den folgenden verwendet.

```Bash
ls | wc -l # Zeilenangabe des ls-Befehls, also Anzahl an Elementen im aktuellen Verzeichnis
```

## IF & ELSE

Verzweigungen sind nach folgendem Schema möglich:

```Bash
if [ $Name != $USER ]
then
    echo "The given name is not equal to your username"
else
    echo "The given name is equal to username"
fi
```

Es ist hierbei zu beachten, dass die obige Syntax fehlerhaft ist, wenn der Variablen *Name* kein Wert zugewiesen wurde. Besser ist deshalb die Verwendung der Schreibweise:

```Bash
if [ "$Name" != $USER ]
  # ...
fi
```

Wenn die Variable hier leer ist, wird ein leerer String verwendet.

### Verknüpfung von Abfragen

```Bash
[ "$Name" == "Max Mustermann" ] && [ "$Age" -eq 21 ]
```

## Schleifen

### For

```Bash
# Wiederholung des Loops für jeden Eintrag in der Reihe
for Variable in {1..42}
do
    echo "$Variable"
done

# Klassischer for-Loop
for ((i=0; i < 3; i++))
do
    echo $i
done

# Zugriff auf Dateien im Loop
for file in file1 file2 file3
do
    cat "$file"
done

# For-Loop mit Output eines Programms
for Element in $(ls)
do
    cat "$Element"
done

```

### While

```Bash
while [ true ]
do
    echo "blabla"
    break
done
```

## Funktionen

```Bash
function myFunction1 ()
{
    echo "Arguments work equal to script arguments: $@"
    echo "-> $1 $2..."
    return 0
}

# Alternativ:
myFunction2 ()
{
    echo "blabla"
    return 0
}

# Aufruf der Funktion
myFunction1 "My name is" $Name
```
