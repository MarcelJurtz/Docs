# Textmanipulation

Fast alles unter Linux ist eine Datei, meistens sind diese Textdateien. ZB sind alle  Konfigurationsdateien Textdateien.

Mithilfe dieser Textdateien können die Anwendungen leicht rekonfiguriert werden,
indem nur der Text angepasst werden muss und die Anwendung anschließend neu gestartet werden muss.


## cat

einfachste Möglichkeit, text darzustellen
```
cat dateiname
```

## head

```
head dateiname
```
zeigt nur die ersten 10 Zeilen der Datei an, anpassbar mithilfe x (Zeilenanzahl)
```
head -X dateiname
```

## tail

```
tail dateiname
```
zeigt die letzten 10 Zeilen an
ebenfalls anpassbar mit ```tail -X``` dateiname


## nl

Bei großen Dateien kann es sinnvoll sein, Zeilennummern auszugeben.
Das erfolgt via ```nl dateiname```


## grep

mithilfe von grep kann ein text gefiltert werden. Beispielsweise werden durch folgenden Befehl

```
cat test.txt | grep abc
```

nur die Zeilen von test.txt ausgegeben, die ‚abc‘ enthalten.
Hierbei wird der Inhalt von test.txt als Eingabe an grep ge’piped’ (|).
Anstelle von cat kann auch nl verwendet werden, um die Zeilennummern zu erhalten.


## sed

sed wird verwendet, um eine Datei nach einem Text zu durchsuchen und anschließend etwas mit diesem zu tun.

Beispiel: Folgender Befehl durchsucht die Datei test.txt nach dem Inhalt ‚abc‘, ersetzt diese durch ‚ABC‘ und speichert die neue datei unter test2.txt

```
sed s/abc/ABC/g test.txt > test2.txt
```

Das ```/g``` sorgt dafür, dass alle auftretenden Elemente überschrieben werden,
ohne dieses wird nur der erste Fund ersetzt.

Falls das an Stelle X (zB 3) auftretende Element ersetzt werden soll, kann die Zahl direkt an Stelle von g eingesetzt werden.
