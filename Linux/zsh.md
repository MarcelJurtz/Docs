# zsh

Z Shell, basiert auf bash mit erweiterter Funktionalität.

Eine Shell läuft im Terminal und führt Befehle aus.
Im Terminal wird standardmäßig die Login-Shell gestartet,
andere Shells können anhand Namen gestartet werden.

Beispiele:
* bash
* zsh
* python

## Installation

Git vorrausgesetzt.

```sudo apt get install zsh```

Pfad: ```which zsh```

Setzen der Login-Shell:

```Bash
# Wizard
chsh
# -> Angabe des Pfads

# Direkt
chsh -s /usr/bin/zsh
```

## Konfiguration

Verwendung der oh my zsh - Konfiguration, alternativ kann der eingebaute Wizard verwendet werden.

* Starten des Konfigurationsprozesses: ```zsh```
* Alternativ: [Oh my zsh](http://www.ohmyz.sh)

Die Konfigurationsdatei befindet sich wie die .bashrc unter ~/.zshrc

### Oh my zsh

Install-Befehl unten in der Seite (curl).

Start des install-Skripts, Re-Login.

## Features

### Git

X hinter git-Verzeichnis, wenn Ordner uncommited Änderungen enthält.

### Autocomplete

Standard Autocomplete, aber auch aus der Mitte des Worts heraus.  
Beispielsweise funktioniert: ocume -> tab -> Documents.

Groß- und Kleinschreibung wird auch korrigiert.
