# Linux Dateisystem

## Überblick

* ```/``` root
* ```/bin``` Standard OS Programme (UNIX), teilweise nur Links auf die Programme
* ```/boot``` Kernel-Dateien (Links)
* ```/dev``` Devices, enthält alle Geräte
  * sd -> Harddrives, Nummerierung für Partitionen
* ```/etc``` Konfigurationsdateien für diverse Programme
* ```/home``` Home-Verzeichnisse für alle User (außer Root)
* ```/lib(64)``` Enthält Libraries (enstpricht .dll unter Windows)
* ```/media``` oder ```/mnt``` Mount-Verzeichnis für Automount (Je nach Distribution)
* ```/opt``` Optionale Software
* ```/proc``` Enthält Verzeichnis für jeden laufenden Prozess zur Kommunikation zw. CPU und Software / User
* ```/root``` Home-Verzeichnis des root-Users
* ```/sbin``` Systemdateien
* ```/tmp``` Temporärdateien, wird bei Reboot geleert
* ```/usr``` Systemtools, Bibliotheken, Programme
* ```/var``` Logdateien etc.

## Dateitypen

ls -la

* ```-``` Textdateien (Ohne Endung)
* ```l``` Symbolic Links
* ```b``` Block -> Storage, auf die Blöcke gespeichert werden können
