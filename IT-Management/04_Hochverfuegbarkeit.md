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
