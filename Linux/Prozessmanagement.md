# Prozessmanagement

Ein Prozess ist ein Programm, welches im Arbeitsspeicher läuft.
Systemprozesse werden unter Linux als daemon/demon bezeichnet und sind oft durch ein ‚d‘ am Ende des Namens gekennzeichnet,  zB httpd

Ausgabe aller laufenden Prozesse:

```
ps aux
	a: all processes
	u: user
	x: processes not associated with a terminal
```

Mithilfe dieser 3 Switches wird ersichtlich, welcher user welchen prozess wann initialisiert hat, und wie der ressourcenverbrauch(%CPU, %RAM) bei diesem ist.

PID = Process identifier

Falls nur begrenzte Informationen benötigt werden, kann der Befehl ps -A verwendet werden.

## top

top ist ähnlich wie ps, gibt jedoch nur die top-prozesse aus, also die Prozesse,
die am meisten ressourcen verbrauchen.
Top ist zudem dynamisch, aktualisiert sich also, wie zB der Taskmanager unter Windows

## kill

mit kill könne Prozesse beendet werden, wenn diese nicht mehr reagieren (ressourcen verbrauchen, aber sich nicht normal schließen lassen). Solche Prozesse werden auch zombies genannt.

zur Identifikation wird die PID verwendet. textEdit unter OSX hat die ID 677 und kann also mit ```kill 677``` beendet werden.

Es gibt diverse Arten von kill, ohne parameter wird der sogenannte kill 15 ausgeführt. Dieser erlaubt dem prozess, aufzuräumen, und anschließend zu beenden.
Falls ein Prozess diesen Befehl nicht ausführen sollte, kann kill -9 verwendet werden, um sofortiges beenden zu erzwingen.


## Prioritäten

Jeder Prozess unter Linux besitzt eine Priorität, welche in Form einer Nummer zwischen 0 und 127 dargestellt wird. 0 ist die höchste, 127 die niedrigste Prioriät.

Die Priorität kann nicht direkt beeinflusst werden, jedoch kann dem Kernel übergeben werden, dass eine spezifische Priorität erhöht oder vermindert werden soll.

hierzu wird der befehl ‚nice‘ verwendet, in Kombination mit einer Zahl zwischen -20 und +19. Auch hier bedeutet die niedrigere Zahl eine höhere Priorität.

Genaue Anwendung hierzu googlen, umständlich.

Reset der Priorität: ```renice prioritätslevel PID```

Befehle ‚sperren‘ oft die Shell bis sie abgeschlossen sind. Um dies zu verhindern, kann ein Befehl in den Hintergrund verlagert werden, um die shell weiterhin zu benutzen. Hierzu einfach ein & an den Befehl anhängen.

Um einen Prozess aus dem Hintergrund in den Vordergrund zu holen: fg
Um einen Prozess aus dem Vordergrund in den Hintergrund zu holen: STRG+Z um diesen zu stoppen, anschließend bg + PID
