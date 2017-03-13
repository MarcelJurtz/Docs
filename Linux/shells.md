# Shells

Die meisten Linux-Distributionen enthalten standardmäßig bash (bourne again shell).  
Alternativ kann aber auch eine andere Shell verwendet werden.
Zsh beispielsweise ist eine recht beliebte Alternative, es gibt aber noch zahlreiche andere shells, wie ash, dash, fish, und tcsh.

## Funktionen einer Shell

Beim Start einer Kommandozeile bzw. eines Terminals unter Linux wird vom System das *Shell*-Programm gestartet. Shells ergänzen die Funktionen der Kommandozeile.

Bash beispielsweise bietet Möglichkeiten zur Autovervollständigung (Dateinamen + Befehle), erweiterte Scripting-Funktionen, eine Befehlshistorie etc. Die Shell wird außerdem von diversen Programmen im Hintergrund genutzt.

## Verschiedene Shells

* 1979: Bourne Shell, nach Stephen Bourne
* Späte 1970er: C Shell nach Bill Joy
* 1989: bash (Bourne again Shell) durch das GNU-Project für POSIX
* ASH (Almquish Shell) für BSD
* DAHS (Debian ASH), Portierung von ASH für Debian
* 1990: zsh (Z Shell), Enthält bash-Features und eigene
* 2005: fish (Friendly Interactive Shell)

## Welche Shell benutzen?

Theoretisch muss keine shell ausgewählt werden, da das OS diese Entscheidung automatisch trifft.
Diese Entscheidung fällt meistens auf bash, so auch bei macOS.
Bash besitzt einige fortgeschrittene Features, welche jedoch außerhalb von shell-skripten kaum genutzt werden.

Auf embedded-linux- oder BSD-Systemen wird meistens die ash shell verwendet. Ash ist eine bourne-basierte shell und größtenteils kompatibel mit bash. Wissen kann somit transferiert werden.
In der leichtgewichtigen ash sind jedoch manche scripting-features nicht verfügbar.


Naheu jede Standard-shell ist bourne-basiert und funktioniert ähnlich, so auch zsh, weshalb diese so beliebt ist.  
Diese neuere shell ist kompatibel mit bash, enthält aber mehr features, wie beispielsweise auto-korrektur, verbessertes autocomplete, nachladbare Module als plugins, globale aliase, die Dateien oder Befehlen zugeordnet werden können, sowie viele weiter.

Der Wechsel von bash zu zsh fällt also leicht - es kommen lediglich neue Funktionen dazu.

## zsh

[Oh my zsh](http://ohmyz.sh) ist ein Tool, welches die Konfiguration von zsh einfacher macht.

Nach der Installation kann zsh mit dem Befehl ```zsh``` gestartet werden. Mit ```exit``` wird die zsh-Instanz beendet. Um die Standard-shell (login shell) zu ändern, wird der Befehl ```chsh``` verwendet. Hierzu wird der vollständige Pfad der Shell benötigt, welcher mit ```which zsh``` herausgefunden werden kann. Dieser liefert beispielsweise ```/usr/bin/zsh``` zurück.  
Wird anschließend ```chsh``` aufgerufen, kann der ermittelte Pfad angegeben werden.
