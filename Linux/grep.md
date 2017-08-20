# Grep

Mit Grep können Textdateien nach bestimmten Inhalten durchsucht werden. Grep steht dabei für "Global regular expression print" und dient somit (wie zu erwarten) zur Visualisierung von Regex-Queries.

grep variable *.md

Durchsucht alle Markdown-Dateien im aktuellen Verzeichnis nach dem Inhalt "variable". Standardmäßig ist die Suche case-sensitiv.

Um die Suche ohne Beachtung von Groß- oder Kleinschreibung durchzuführen kann der Flag -i verwendet werden.

Um beim Durchsuchen mehrerer Dateien nicht die Stellen, sondern lediglich die Dateien anzuzeigen, die den Text beinhalten, wird der Flag -l verwendet.
Bei -L wird das invertiert, also nur Dateinamen angegeben, die den Text nicht enthalten.

Der Tag -c gibt die Anzahl von Auftritten der Suche je Datei an.

Mit -n wird der Inhalt und die Zeilennummer angegeben.

-w legt fest, dass nur 1:1 Auftritte relevant sind.
Das heisst, im Fall von "variable" würde "variablen" nicht gefunden werden.

Ein -R sucht zusätzlich in Unterordnern.


