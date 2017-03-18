# Konfiguration

* /etc/pacman.d/

  mirrorlist --> Verwaltung der Mirror-Server für die Repositories.
  Auffrischen mit Reflector:

  reflector --verbose -l 5 -p https --sort rate --save /etc/pacman.d/mirrorlist
  * verbose: Informationen ausgeben
  * l 5: Oberste 5 Server verwenden
  * p https: Protokollauswahl
  * sort rate: Sortierung nach Schnelligkeit, absteigend
  * --save /etc/pacman.d/mirrorlist: Speicherpfad

* /etc/pacman.conf

  Verschiedene Einstellungsmöglichkeiten, z.B.
  * Holdpkg: Pakete, die nicht deinstalliert werden dürfen
  * Ignorepkg: Pakete, die bei Updates ignoriert werden
  * SigLevel: Verifikation der Quelle

* /var/cache/pacman/pkg

  Enthält die Pakete aller installierter Software sowie deren alte Versionen
  * Ausgabe der aktuell installierten Version: pacman -Q paketname
  * Ausgabe mit zusätzlichen Informationen: pacman -Qi paketname

# Befehle

* pacman -S paketname - Paket installieren
* pacman -Si paketname - Informationen zu (noch nicht) installiertem Paket anzeigen
* pacman -U paketname - Paket installieren (kein Repository, zB über makepkg -sr)
* pacman -Sy - Paket installieren mit gleichzeitiger Aktualisierung der Paketdatenbank
* pacman -Syu - Update aller Pakete (ignorepkg-Pakete werden mit Warnungen gekennzeichnet)
* pacman -Rns paketname - Deinstallation eines Pakets inklusive Abhängigkeiten
* pacman -Ss paketname - Suche nach Paketen mit (ähnlichen) Namen auf Servern
* paccache -r - Cache aufräumen, die letzten 3 Versionen der Pakete werden behalten
* bacman paketname - Herstellen eines Pakets aus installierter Software
* checkupdates - Prüft auf vorhandene Updates
