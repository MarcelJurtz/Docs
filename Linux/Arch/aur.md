# Arch User Repository

![Arch User Repository](https://aur.archlinux.org/)

User können im AUR Packagebuilds hochladen. Diese erhalten sie von den Websites der Programmierer.
Der Anwender, der einen Packagebuild hochgeladen hat, ist für diesen zuständig (Updates etc.).
Mit diesem Packagebuild kann ein Programm erstellt (bzw. kompiliert) werden, welcher von Pacman dann verwaltet wird (Update, Deinstallation).

## Installation eines Pakets aus dem AUR

Beispielinstallation: pacaur (AUR-Helper).

Auf jeder Paketseite im AUR findet sich eine Liste von Dependencies, die das Paket benötigt,
sowie Kommentare anderer User, welche sich oft zur Fehlersuche eignen.

1. Verzeichnis für das Paket erstellen.
2. Snapshot -> URL kopieren -> wget (Alternativ: GitHub-Repository klonen)
3. tar -xzvf
4. cd
5. makepkg -sr
  * s --> Abhängigkeiten installieren
  * r --> Abhängigkeiten nach Installation wieder entfernen
  * i --> Gleich Installieren
6. Bei Fehlermeldung: Abhängigkeit nicht in offiziellem Repository:
  * AUR-Seite des Programms - Dependencies - Entsprechende Seite
  * Schritte von Oben für das Programm wiederholen
7. Bei Fehlermeldung: GPG-Signatur konnte nicht überprüft werden:
  * Key nicht im Pacman-Keyring vorhanden, muss heruntergeladen werden
  * Ausgabe der Keys: gpg --list-keys
  * Key-Befehl (im Bsp. Pacaur in den AUR-Kommentaren): gpg --recv-keys --keyserver server key
8. makepkg -rs nochmal probieren
9. cd -> ls Paket (.tar.gz) liegt nun vor
10. Zu Pacman hinzufügen: pacman -U paketname

## AUR-Helper

Vereinfachung der Installation aus dem AUR.

Installiert: Pacaur  
Benutzung: Gleiche Befehle wie pacman
