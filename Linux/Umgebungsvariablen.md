# Umgebungsvariablen

## Umgebungsvariablen einsehen: set
set listet alle Umgebungsvariablen, von Anwendern definierte Funktionen, und Aliase auf.
Umgebungsvariablen werden immer in UPPER CASE geschrieben.
Um den Wert einer Variablen auszugeben, wird echo $Variablenname verwendet.

Beispielsweise enthält die HISTSIZE-Umgebungsvariable den Wert der Anzahl von Befehlen, die in der Verlauf-Datei gespeichert sind.
Um zB Spuren zu verwischen kann diese Anzahl zB auf 0 gesetzt werden.

HISTSIZE=0 (ohne Leerzeichen!)

Änderungen an den Umgebungsvariablen sind nur für die aktuelle Umgebung,
sobald das Terminalfenster geschlossen wird, wird der Wert wieder zurückgesetzt.

Um den Wert zu behalten muss die Variable exportiert werden: export HISTSIZE

zB Kann auch der eingabetext des terminalfensters geändert werden:
PS1=„Text“
Diese Änderung betrifft jetzt nur die erste Instanz des Terminals


## PATH-Variable:

Die Path-Variable ist die wichtigste Umgebungsvariable. Sie enthält die Verzeichnisse, die die Programme wie cd, ls, … enthält. Ohne diese Variable werden Programmpfade nicht gefunden, obwohl die Programme existieren.

Wenn ein Programm mithilfe des terminals verwendet wird, welches aber keinen Eintrag in der PATH-Variable besitzt, muss jedes Mal in das entsprechende Verzeichnis navigiert werden. Es kann jedoch auch ein Eintrag hinzugefügt werden:

PATH=$PATH:/pentest/wireless/aircrack-ng

Der Pfad wurde so um die aircrack-ng-Datei erweitert. Es sollten jedoch nicht zu viele Pfade hinzugefügt werden, da hierdurch das System verlangsamt werden kann.
