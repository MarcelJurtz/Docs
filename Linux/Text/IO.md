# Input & Output

## STDOUT

```Bash
# Schreibt "Hello World" in die Datei "somefile.txt"
# Falls diese existiert, wird sie überschrieben
echo "Hello World" > somefile.txt

# Wie oben, jedoch wird die Datei im Fall der Existenz ergänzt
echo "Hello World" >> somefile.txt
```

## STDIN

Neben dem Output kann auch der Input von Befehlen angepasst werden:

```Bash
# cat verwendet "somefile.txt" als STDIN
cat < somefile.txt
```

## Kombination

Umleitung von STDIN und STDOUT kann kombiniert werden:

```Bash
cat < somefile.txt > somenewfile.txt
```

## STDERR

Umleitung der Fehlerausgabe.

Beispiel:
```Bash
$ ls /fake > fake.txt
ls: cannot access /fake: No such file or directory
```

Für STDERR gibt es keine so schöne Schreibweise, weshalb *file-descriptors* verwendet werden.

Diese lauten wie folgt:
* stdin: 0
* stdout: 1
* stderr: 2

Folgender Code leitet nun sowohl STDERR als auch STDOUT an die Datei "fake.txt" weiter.

```Bash
$ ls /fake > fake.txt 2>&1
```

Die zuvor angezeigte Fehlermeldung ist nun in diesem File hinterlegt.
Der Code sendet das Ergebnis des ls-Befehls an die Datei "fake.txt" und leitet anschließend STDERR an STDOUT anhand *2>&1*. Die Reihenfolge spielt hier eine Rolle: 2>&1 sendet STDERR an die Stelle, auf die STDOUT zeigt. Hier zeigt STDOUT auf eine Datei, also wird STDERR ebenfalls an eine Datei geleitet.

```Bash
# Alternative Kurzschreibweise
$ ls /fake &> fake.txt
```

Um einen Output komplett loszuwerden, kann dieser nach /dev/null geleitet werden.

```Bash
$ ls /fake 2> /dev/null
```
