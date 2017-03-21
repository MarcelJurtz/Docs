# Rechteverwaltung

## Rechte einsehen:

Um die Rechte an Dateien zu sehen, kann der ls-Befehl mit dem Parameter l (long) verwendet werden.  
Nun werden Informationen mit Berechtigungen zu den enthaltenen Dateien angegeben.

Das erste Zeichen in jeder angezeigten Zeile zeigt an, ob es sich beim aktuellen Eintrag um eine Datei oder ein Verzeichnis handelt.

```
	d - Directory
	- - File
```

Der nächste Abschnitt identifiziert die Berechtigungen.
```
	r (read) w (write) x (execute)
```

Die Berechtigungen sind in 3 Gruppen aufgeteilt: Owner, Group, Public

```
r w -   r - -   - - -
Owner: read & write
Group: read
Public: Nichts
```

## Berechtigungen ändern:
chmod-Befehl ändert Berechtigungen für eine Datei.
chmod kann als root und als owner der Datei durchgeführt werden.

Die Berechtigungen können jeweils als Nummern dargestellt werden.
Aufbau:

```
r w x
4 2 1 = 7
```

Die beispielhafte Berechtigung oben für alle 3 Gruppierungen gemeinsam wäre also

```
r w x   r w x   r w x
4 2 -   4 - -   - - -
6	 4	 -
640
```

Die Berechtigung kann nun mit dieser Zahl angepasst werden.
Beispielsweise soll dir Gruppe auch schreiben dürfen, und public lesen:
chmod 664 dateiname
