# Datenschutz und Datensicherheit

Datenschutz: Vertraulichkeit der (beliebigen) Daten.  
Gem�� des Datenschutzgesetzes bezieht sich Datenschutz nur auf personenbezogene Daten,
weshalb diese Definition hier ung�nstig ist.

Datenschutz = Schutz vor unberechtiger Informationsverarbeitung.  
Datensicherheit = Schutz vor Manipulation oder Verlust der Daten.

Sicherheit bezeichnet die Abwesenheit von Gefahren.
* Integrit�t
* Vertraulichkeit
* Verf�gbarkeit

Probleme:

* Crackerangriffe
* Unsicher IoT-Ger�te
* USB-Exploits

Gr�nde f�r Datensicherheit (Absteigene Relevanz):

* Vermeidung von Datenverlust
* Aufrechterhaltung des operationellen Gesch�ftsablaufs
* Gesetzliche Vorgaben
* Schutz vor Imageverlust
* Vertragsbedingungen

Rechtliche Anforderungen (Ausschnitt):

* Sorgfaltspflicht
* Aufbewahrungspflicht
* Bundesdatenschutzgesetz
* Fernmeldegeheimnis

Richtlinien anhand des IT-Grundschutz-Katalogs des BSI (Bundesamt f�r Sicherheit).  
https://www.bsi.bund.de/DE/Themen/ITGrundschutz/itgrundschutz_node.html

Beteiligte Personen

* Systemadministratoren
* Sicherheitsbeauftragte
* Sicherheitsinspektoren
* Programmierer
* Anwender
* Servicetechniker (intern und extern)

Gefahren entstehen durch verschiedene Ursachen, beispielsweise h�here Gewalt (Unwetter), technisches Versagen, 
organisatorische Fehler (fehlendes Sicherheitskonzept), menschliches Versagen (versehentlich) oder absichtliche Manipulation (intern und extern).

Organisatorische Fehler umfassen Fehler im Ablauf der EDV des Unternehmens, fehlende Sicherheitskonzepte, oder Probleme bei der Vergabe von Berechtigungen.
Gefahren aus dieser Kategorie erm�glichen Gefahren in anderen Kategorien.

Menschliche Fehlhandlungen entstehen (im Gegensatz zu vors�tzlichen Handlungen) unabsichtlich. 
Beispiele hierf�r w�ren versehentliches �ndern / L�schen von Dateien,
Senden von E-Mails an falsche Empf�nger, oder schlechten Umgang mit Kennw�rtern.

Die hierzu entgegenstehenden vors�tzliche Handlungen k�nnen von externen und internen Personen vorgenommen werden.
Autorisierte Personen k�nnen ihre Rechte missbrauchen, Angreifer k�nnen versuchen, unautorisierten Zugriff zu erlangen.

## Sicherheitsmanagement

Regelung der
* Gesamtverantwortung f�r IT-Sicherheit
* Sicherheitsziele
* Ressourcenbereitstellung
* ...

### Klassifikation von Schwachstellen

|   | Ebene           | Inhalt                            | Beispiel                            | Stelle              |
|---|-----------------|-----------------------------------|-------------------------------------|---------------------|
| 5 | Semantik        | Schutz vor Betrug                 | Phishing                            | Fachabteilung       |
| 4 | Logik           | Absicherung von Prozessen         | Benutzer-Lock-out                   | Fachabteilung       |
| 3 | Implementierung | Vermeiden von Programmierfehlern  | SQL-Injcetion, Cross Site Scripting | Entwickler          |
| 2 | Technologie     | Wahl und Einsatz der Technologie  | Verschl�sselung                     | Entwickler, Betrieb |
| 1 | System          | Absicherung der Software          | Konfiguration, Bekannte Fehler      | Betrieb             |
| 0 | Netzwerk / Host | Absicherung von Netzwerk und Host | Konfiguration                       | Betrieb             |


### Sicherheits-Management-Prozess

```
TODO
```

### IT-Sicherheitsmanagement nach BSI

Initiierung des Sicherheitsprozesses:
* Verantwortung der Leitungsebene
* Konzeption und Planung
* Erstellung einer Leitlinie zur Informationssicherheit
* Aufbau einer Informationssicherheitsorganisation
* Bereitstellung von Ressourcen
* Einbindung aller Mitarbeiter

Anschlie�end (Itarativ):
* Erstellung einer Sicherheitskonzeption
* Umsetzung der Sicherheitskonzeption
* Aufrechterhaltung und Verbesserung

### Interessenvertreter

* Datenschutzbeauftragter
* Betriebsrat
* Systemersteller
* Benutzer
* IT-Sicherheitsbeauftragter
* Revision
* Systembetreiber
* CERT (Computer Emergency Response Team) / CSIRT (Computer Security Incident Response Team)

Ein Datenschutzbeauftragter wird ben�tigt, wenn mindestens 10 Personen im Unternehmen mit der Verarbeitung personenbezogener Daten besch�ftigt sind.
�ffentliche Stellen haben immer einen Datenschutzbeauftragten anzustellen. Dieser ben�tigt technische, organisatorische und juristische Kenntnisse.

### Sicherheitsmanagement

Auf einen Teil des gesamten Risikopotentials werden Schuztma�nahmen angewandt. Ein weiterer Teil wird durch Versicherungen abgedeckt, 
dies bietet sich vor allem bei Risiken mit geringer Eintrittswahrscheinlichkeit und hohem Schaden an.

### Methodik nach IT-Grundschutz

```
TODO
```

## Ma�nahmen

Hauptanforderungen sind die Forderungen nach Wirksamkeit, Wirtschaftlichkeit, Einfachheit und Sicherheit. Diese sollen durch organisatorische, technische, sowie personelle Ma�nahmen erreicht werden.

Organisatorische Ma�nahmen werden grunds�tzlich durch ein Sicherheitskonzept geregelt, welches vom Sicherheitsbeauftragten erstellt wird.
Dieses bestimmt verschiedene Richtlinien:
* Anforderungen an Kennw�rter
* Rechte / Benutzergruppen
* Notfallsystem
* Kryptosystem

Technische Ma�nahmen beinhalten Ma�nahmen zur Erhaltung der Verf�gbarkeit, zum Einsatz von Firewalls, sowie Intrusion Detection Systeme.

Personelle Ma�nahmen umfassen die Sensibilisierung von Nutzern, beispielsweise zum Sperren von PCs. 
Dies wird durch Schulungen erreicht, Stichwort: "Awareness".

Man unterscheidet allgemein zwischen drei Varianten:

* Pr�ventiv: Einschr�nkung / Vermeidung von Gefahren im Vorfeld.
* �berwachend: Erkennung von Angriffen bei deren Eintritt. Dies ist rechtlich heikel, momentan besteht der L�sungsansatz in der Speicherung von �berwachungsdaten, welche aber nur in konkreten Angriffsf�llen gelesen werden d�rfen.
* Reaktiv: Reaktion auf Angriffe zur Verringerung von Schaden, sofortige Gegenma�nahmen.

Die Ma�nahmen k�nnen bewertet werden, indem die Wirkung, Kosten, Kombination mit anderen Ma�nahmen, sowie Benutzerfreundlichkeit bewertet wird.

Die Dokumentation der Sicherheitsstrategie f�r alle Mitarbeiter findet in verst�ndlicher Form in den IT-Sicherheitsrichtlinien statt.

```
Inhalte- TODO
```
