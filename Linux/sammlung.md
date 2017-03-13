# w
w liefert detaillierte Informationen als *who*.

Uptime, Uhrzeit, Anzahl angemeldeter User, load average (CPU-Auslastung)  
Jede Session (Prozess) zählt als einzelner User.

TTY: Teletype, zB pts/5 -> sudo-Terminal  
FROM: Enthält IP-Adresse bei Remote-Zugriff  
Logintime, Idle-Time, CPU-Time, What ausgeführt wird.

# top

Auflistung der Prozess, Sortierung nach CPU-Belastung. Alternative: htop.

# netstat

* -t: tcp-ports
* -u: udp-ports
* -p: Programm, das die Ports nutzt
* -l: listening Ports
* -n: Numerisch
* -...

Proto - Kennzeichnung des Protokolls, angehängte *6* bei IPv6.
PID wird nur bei Nutzung als root angegeben.
