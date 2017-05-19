# Hochverfügbarkeit

Ziel: Möglichkeit zur Weiterarbeit trotz Ausfällen.

*Ausfall*: In Servicezeit nicht erreichbar.

Schutz vor

* Vandalismus
* Angriffen
* Viren
* Bedienerfehler
* ...

Ausfälle werden differenziert in geplante und ungeplante Ausfälle, welche jeweils weiterhin klassifiziert werden in Kategorien wie Hardware, Software, Infrastruktur, Umwelt, Menschliches Versagen.

## Definition

Oft werden bei Angaben von Verfügbarkeiten die Ausfallzeiten in Stunden / Tagen angegeben. Dies ist schlecht, da ein herunterbrechen auf ein Jahr meist sinnlos ist.
Eine bessere Definition ist die, dass die Verfügbarkeit die Wahrscheinlichkeit ist, mit der ein System zu einem bestimmten Zeitpunkt einsetzbar ist. Ist dies nicht der Fall, spricht man von einem Ausfall.

Auch ein langsames System kann als Ausfall gewertet werden!

## Kennzahlen

* MTBF: Mean Time Between Failure
* MTBDL: Mean Time Between Data Loss
* MTTR: Mean Time To Repair

Verfügbarkeit = MTBF / (MTBF + MTTR)

Zur Verbesserung der Verfügbarkeit gelten also zwei Ziele:
* MTTR verringern
* MTBF vergrößern

Weitere Kennzahlen:
* Annualized Failure Rate (AFR): Beschreibt die jährliche Ausfallrate in Bezug auf die Gesamtanzahl. AFR = 1 / MTBF * Betriebsstunden
* Component-Design-Life (CDL): Vorhergesehene maximale Lebensdauer. Bezieht sich auf den  Einsatz unter optimalen Bedingungen.
* Recovery Point Objective (RPO): maximale Zeit zwischen zwei Sicherungen
* Recovery Time Objective (RTO): maximale Betriebsunterbrechungszeit

### Beispielhafte Berechnung

* Controller mit V = 99%
* 2 Festplatten mit jeweils V = 98,2%

V(DH) = V(C ∧ P1 ∧ P2)  
= V(C) * V(P1) * V(P2)  
= 0,99 * 0,982 * 0,982  
= 0,9547

Durch Redundanzen kann diese stark verbessert werden: Ein Ausfall liegt nun vor, wenn keins der Systeme verfügbar ist.

V(C) = 1 - 0,1 * 0,1  
= 0,9999

V(P1) = 1 - (1 - 0,982) * (1 - 0,982)  
= 0,9997
V(P2) = 1 - (1 - 0,982) * (1 - 0,982)  
= 0,9997

V = 0,9999 * 0,9997 * 0,9997  
= 0,9993

Durch Redundanz wurde die Verfügbarkeit von 95,47% auf 99,93% gesteigert.

## Einschränkungen

* Kosten → Bei voller Redundanz doppelt
* Leistung
* Umfeld

## Grundprinzipien

* Vemeidung eines Single Point of Failure → Keine zentralen Ausfallstellen dürfen vorliegen
* Ausfall darf nur begrenzten Einfluss haben
* Reparatur muss ohne Unterbrechung möglich sein

## Stufen der Hochverfügbarkeit

* Level 1: Basisverfügbarkeit
  * Kein Schutz vor Systemausfällen
  * Tägliche Datensicherungen
  * Ausfälle werden akzeptiert
* Level 2:
  * Ausfälle sind seltener als bei Level 1
  * Keine Datenverluste
  * Hardwareprüfung durch Diagnoseprogramme
  * RAID-Systeme zur Absicherung gegen Festplattenausfälle
  * Transaktionsorientierte Dateisysteme
* Level 3:
  * System ist vollständig redundant
* Level 4:
  * Zusätzliches Abfangen eines Gebäudes / Rechenzentrums

## Systemdesign

### Speichermedien

Aktuelle Fesplatten-MTBF: 1 Mio. Stunden. Wenn die Ausfallwahrscheinlichkeit gleichverteil ist, so fällt bei 500 Festplatten alle 146 Tage eine aus. Die Ausfallrate bei Festplatten ist bei der Einlaufphase sowie im Ausfallmodus nach der normalen Alterung besonders hoch, Hardwarehersteller verkaufen sie deshalb erst nach der Einlaufphase.

Die Zeiten sind von den Herstellern zudem optimistisch und unter optimalen Bedingungen ermittelt, zudem bestehen Begrenzungen wie Schreibzugriffe auf SSDs. In der Praxis beträgt die Festplattenlebensdauer etwa 3-4 Jahre.

### RAID

Redundant Array of Independent (früher: Inexpensive) Disks.
Schneller Plattenaustausch im Fall eines Ausfalls ist erforderlich, weshalb passende Festplatten stets auf Lager sein sollten.

#### RAID 0: Strip Array

```
      +-------+
      |   B1  |
      +-------+           +-------+     +-------+     +-------+
      |   B2  |           |   B1  |     |   B2  |     |   B3  |
      +-------+           +-------+     +-------+     +-------+        
      |   B3  |           |   B4  |     |   B5  |     |   B6  |
      +-------+           +-------+     +-------+     +-------+
      |   B4  |                 Physikalische Festplatten
      +-------+
      |   B5  |
      +-------+
      |   B6  |
      +-------+
 Logische Festplatte
```

* Keine Redundanz
* Beispielsweise bei Videobearbeitung im Einsatz, da gleichzeitiges Lesen und Schreiben möglich

#### RAID 1: Mirror

```
      +-------+           +-------+     +-------+
      |   B1  |           |   B1  |     |   B1  |
      +-------+           +-------+     +-------+
      |   B2  |           |   B2  |     |   B2  |
      +-------+           +-------+     +-------+
      |   B3  |           |   B3  |     |   B3  |
      +-------+           +-------+     +-------+
      |   B4  |           |   B4  |     |   B4  |
      +-------+           +-------+     +-------+
      |   B5  |           |   B5  |     |   B5  |
      +-------+           +-------+     +-------+
      |   B6  |           |   B6  |     |   B6  |
      +-------+           +-------+     +-------+
 Logische Festplatte     Physikalische Festplatten
```

* Vollständige Redundanz
* Beispielsweise bei WebServern im Einsatz
* Performancesteigerung beim Lesen
* Doppeltes Speichervolumen benötigt

#### RAID 2 / 3 / 4: Strip Array mit ECC

ECC: Error Correcting Code

```
      +-------+
      |   B1  |                                                            ECC
      +-------+           +-------+     +-------+     +-------+         +-------+
      |   B2  |           |   B1  |     |   B2  |     |   B3  |         | 1,2,3 |
      +-------+           +-------+     +-------+     +-------+         +-------+
      |   B3  |           |   B4  |     |   B5  |     |   B6  |         | 4,5,6 |
      +-------+           +-------+     +-------+     +-------+         +-------+
      |   B4  |                 Physikalische Festplatten
      +-------+
      |   B5  |
      +-------+
      |   B6  |
      +-------+
 Logische Festplatte
```

Beim Ausfall von Beispielsweise B2:

ECC123 = B1 XOR B2 XOR B3  
B2 = ECC123 XOR B1 XOR B3  
B2 = B1 XOR B2 XOR B3 XOR B1 XOR B3  
B2 = B1 XOR B1 XOR B2 XOR B3 XOR B3  
B2 = B2

Unterschiede zwischen RAID 2, 3 und 4:
* RAID 2: Reihum speichern von Bits
* RAID 3: Reihum speichern von Bytes
* RAID 4: Reihum speichern von Blöcken

Mit den RAID-Stufen 2,3 und 4 lassen sich beliebig viele Festplatten absichern. Bei einem gleichzeitigen Ausfall von zwei Platten entsteht Datenverlust.

Es bestehen keine Geschwindigkeitsvorteile beim Schreiben, da die ECC-Platte bei jedem Schreibzugriff belastet wird.

#### RAID 5

```
      +-------+
      |   B1  |
      +-------+           +-------+     +-------+     +-------+     +-------+
      |   B2  |           |   B1  |     |   B2  |     |   B3  |     | 1,2,3 |
      +-------+           +-------+     +-------+     +-------+     +-------+
      |   B3  |           | 4,5,6 |     |   B4  |     |   B5  |     |   B6  |
      +-------+           +-------+     +-------+     +-------+     +-------+
      |   B4  |                 Physikalische Festplatten
      +-------+
      |   B5  |
      +-------+
      |   B6  |
      +-------+
 Logische Festplatte
```

Bei RAID 5 wird die Fehlerkorrektur reihum verteilt. Hierdurch besteht die Möglichkeit zu schnellerem Schreibzugriff.

#### RAID 6

* Toleriert zwei Festplattenausfälle
* Ausfallinformationen doppelt gespeichert anhand des Reed-Solomon-Codes
* Komplexe Berechnung, welche diese Systeme teuer macht

#### RAID 7

* Kein Standard, Marketing-Strategie der *Storage Computer Corporation*
* Asynchrones Schreiben durch große Caches
* Kein Einsatz für Datenbanken, da das WAL-Prinzip verletzt wird

#### RAID 10

```
                          +-------+     +-------+
                          |   B1  |     |   B1  |
      +-------+           +-------+     +-------+
      |   B1  |           |   B4  |     |   B4  |
      +-------+           +-------+     +-------+
      |   B2  |
      +-------+           +-------+     +-------+
      |   B3  |           |   B2  |     |   B2  |
      +-------+           +-------+     +-------+
      |   B4  |           |   B5  |     |   B5  |
      +-------+           +-------+     +-------+
      |   B5  |
      +-------+           +-------+     +-------+
      |   B6  |           |   B3  |     |   B3  |
      +-------+           +-------+     +-------+
Logische Festplatte       |   B6  |     |   B6  |
                          +-------+     +-------+
                         Physikalische Festplatten
```

#### RAID 0+1

```
      +-------+
      |   B1  |
      +-------+           +-------+     +-------+     +-------+
      |   B2  |           |   B1  |     |   B2  |     |   B3  |
      +-------+           +-------+     +-------+     +-------+
      |   B3  |           |   B4  |     |   B5  |     |   B6  |
      +-------+           +-------+     +-------+     +-------+
      |   B4  |
      +-------+           +-------+     +-------+     +-------+
      |   B5  |           |   B1  |     |   B2  |     |   B3  |
      +-------+           +-------+     +-------+     +-------+
      |   B6  |           |   B4  |     |   B5  |     |   B6  |
      +-------+           +-------+     +-------+     +-------+
 Logische Festplatte            Physikalische Festplatten
```

Ein Plattenausfall bei RAID 0+1 bedeutet einen kompletten Seitenausfall.

#### RAID 51

```
      +-------+
      |   B1  |
      +-------+           +-------+     +-------+     +-------+     +-------+
      |   B2  |           |   B1  |     |   B2  |     |   B3  |     | 1,2,3 |
      +-------+           +-------+     +-------+     +-------+     +-------+
      |   B3  |           | 4,5,6 |     |   B4  |     |   B5  |     |   B6  |
      +-------+           +-------+     +-------+     +-------+     +-------+
      |   B4  |
      +-------+           +-------+     +-------+     +-------+     +-------+
      |   B5  |           |   B1  |     |   B2  |     |   B3  |     | 1,2,3 |
      +-------+           +-------+     +-------+     +-------+     +-------+
      |   B6  |           | 4,5,6 |     |   B4  |     |   B5  |     |   B6  |
      +-------+           +-------+     +-------+     +-------+     +-------+
 Logische Festplatte            Physikalische Festplatten
```

Hier sind 3 Festplattenausfälle immer abgedeckt.

#### Vergleich

| RAID                            | 0 | 1 | 2-4 | 5       | 6       | 10 (01) | 51      |
|---------------------------------|---|---|-----|---------|---------|---------|---------|
| Platten mit Fehlerkorrektur     | n | 2 | n+1 | n+1     | n+2     | 2n      | 2(n+1)  |
| Maximaler Lesefaktor            | n | 2 | n   | n+1     | n+2     | 2n      | 2(n+1)  |
| Maximaler Schreibfaktor         | n | 1 | 1   | (n+1)/2 | (n+2)/3 | n       | (n+1)/2 |
| Ausfallsicherheit (Platzierung) | 5 | 3 | 4   | 4       | 2       | 2       | 1       |

RAID 1 wurde hier höher platziert als RAID 2-4 bzw. RAID 5, da weniger Platten für die gleiche Ausfallsicherheit benötigt werden. Allgemein ist zu beachten, dass die Ausfallwahrscheinlichkeit einer Platte bei einer höheren Gesamtmenge ebenfalls höher ist.

### Systemdesign auf Dateiebene

Sogenannte *Journaling File Systems* (funktionsorientierte Dateiesysteme) protokollieren Änderungspositionen, bei einem Absturz wird die letzte Zugriffsstelle geprüft. Allgemein wird hierdurch die Performance gesenkt, jedoch wird durch diese Maßnahme verhindert, dass die ganze Platte geprüft werden muss, was wiederum die MTTR senkt.

### Zentrale Datensicherung

Problem von Datensicherungen:
* Netzwerk-Kapazität
* Server-CPU-Belastung

#### SAN: Storage Area Network

Aufbau eines eigenen Netzwerks für Backupzwecke, somit wird das produktiv-Netzwerk nicht belastet.

#### Virtual Tape Libraries

Anwenden virtueller Bandlaufwerke zum Speichern auf Platte. Daten werden *dedupliziert*, wodurch doppelt vorhandene Daten (z.B. Lokalkopien oder Konfigurationsdateien) nur einmal gespeichert werden.

#### Replikation und Mirroring

Problem: Viel Zeit für Backups bei großen Datenmengen.  
Lösung: Mirroring / SANs

Beim Mirroring sind Spiegelplatten räumlich entfernt vorhanden. Hierdurch wird der Katastrophenfall abgedeckt, jedoch besteht in der Praxis aus Geschwindigkeitsgründen ein
maximaler Abstand von 10 km (Glasfaser) bei synchroner Übertragung. Oft wird jedoch absichtlich ein Zeitabstand von ~2 Stunden gewählt, um beispielsweise Datenverluste durch Viren oder Angriffe zu verhindern.

Bei der synchronen Replikation gilt der Schreibvorgang als abgeschlossen, wenn die Ankunft vom entfernten Server bestätigt wurde. Bei der asynchronen Replikation wird vermerkt (Log), dass die Datei übertragen werden muss. Bei einem Ausfall des Rechenzentrums gehen also die Daten,
die in der Zwischenzeit angefallen sind, verloren. Hier ist auch die räumliche Entfernung irrelevant.


### Cluster

* Steigerung der Performance durch mehrere Applikationsserver
* Bei einem Ausfall sinkt lediglich die Performance

Anforderungen an Cluster:
* Zentrale Administration (Single Point of Administration)
* Einzelnes Systemabbild
* Kein Single Point of Failure zur Garantie hoher Verfügbarkeit
* Skalierbarkeit

#### Loadbalancing

Verteilung der Last auf gleichartige Applikationsserver:
* Least-Connections: Knoten mit geringsten Verbindungen erhält nächste Verbindung
* Least-Cpu-Usage: Knoten mit geringster CPU-Auslastung erhält nächste Verbindung
* Round-Robin: Zyklische Verteilung der Verbindungen
* Fixed: Fest zugewiesene Verteilung
* Random: Zufällige Serverauswahl

Problematisch hierbei ist, dass die Verteilung auf Momentaufnahmen basiert. Bei den ersten beiden Varianten können verschiedene Ausnahmen vorliegen,
die die Auswahl ineffizient gestalten. SAP verwendet Fixed Balancing und weist beispielsweise jeder Abteilung einen eigenen Applikationsserver zu.
Hierdurch wird das Caching (Puffer) performanter gestaltet, da immer auf die gleichen Daten zugegriffen werden muss (Stammdaten).

#### Fail-Over-Cluster

* Alle Knoten werden produktiv eingesetzt
* Bei einem Ausfall übernimmt ein anderer Knoten, hierzu müssen Peripherie, Anwendungen und IP sowie MAC-Adressen automatisch abgeglichen werden
* Problem: Aktuelle Benutzeraktion kann bei einem Ausfall nicht zu Ende geführt werden.

#### Takeover Cluster

* Server nehmen Aufträge der Clients entgegen
* Alle Aktionen eines Servers werden von einem weiteren mitverfolgt
* Benötigt hierfür ausgelegte Software
* Anwendungsbereich: Datenbankserver mit sehr hoher Verfügbarkeit

#### n+1-Konzepte

* Ein Ersatzserver für mehrere Server
* Beim Ausfall eines Servers springt der Ersatzserver für diesen ein
* Problematisch beim Ausfall mehrerer Server, mögliche Erweiterung zu n+m Lösung

#### Redundanz der Software-Prozesse

Alternativ kann auch der Client anhand eines Multicasts bestimmen,
welcher Server die Anfrage beantworten soll. In der Regel wird hierzu der Server mit der schnellsten Antwort verwendet.
Die Ermittlung der Server erfolgt beispielsweise anhand eines Nameservers.

## Brandschutz

Vorbeugung:

* Baulich
* Technisch
* Organisatorisch

Bereits beim Bau des Rechenzentrums ist auf passende Materialien zu achten.
Löschungsmöglichkeiten mit Gasen (CO2, Stickstoff, Argon), alternativ Verringerung des Sauerstoffsanteil
(Brände werden ab ~15% verhindert (entspricht ~3000m.), für bessere Arbeit durch Menschen in der Praxis meist ~17% (entspricht ~1800m.).
Im Brandfall wird der Sauerstoff durch Zugabe von Stickstoff auf 15% verringert.

## Stromversorgung

Durchgehende Stromversorgung wird durch redundante Zuleitung ins Rechenzentrum, redundante Netzteile oder USVs realisiert,
wobei letztere lediglich eine Zwischenversorgung, beispielsweise zum sauberen Herunterfahren, gewährleisten.
Neuere Möglichkeit: Schwungrad, Antrieb nach einem Ausfall durch Trägheit.

## Kosten

Bei der Planung von Hochverfügbarkeitssystemen ist zwischen Kosten der möglichen Schäden und Kosten für die Sicherheit abzuwägen
und hierbei das optimale Kosten-/Nutzen-verhältnis zu treffen.