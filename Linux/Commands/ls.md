# ls

Mit den ls-Befehlen werden diverse Auflistungen erzeugt.

## lsof

List open files.

Listet alle geöffneten Dateien auf.

```bash
# Nur obere Ergebnisse auflisten:
lsof | head
# -> Liefert Header
```

Anhand der Kopfzeile zeigt sich folgende Struktur:

* NAME: Pfad der Datei
* COMMAND: Befehl
* PID: Process-ID
* User: Anwender, für den der Prozess läuft
* FD: File Descriptor
* TYPE
* DEVICE
* SIZE/OFF
* NODE
* NAME

Meist wird lediglich der Pfad (NAME) benötigt, sowie COMMAND und PID.
