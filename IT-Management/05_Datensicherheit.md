# Datenschutz und Datensicherheit

Datenschutz: Vertraulichkeit der (beliebigen) Daten.  
Gemäß des Datenschutzgesetzes bezieht sich Datenschutz nur auf personenbezogene Daten,
weshalb diese Definition hier ungünstig ist.

Datenschutz = Schutz vor unberechtiger Informationsverarbeitung.  
Datensicherheit = Schutz vor Manipulation oder Verlust der Daten.

Sicherheit bezeichnet die Abwesenheit von Gefahren.
* Integrität
* Vertraulichkeit
* Verfügbarkeit

Probleme:

* Crackerangriffe
* Unsicher IoT-Geräte
* USB-Exploits

Gründe für Datensicherheit (Absteigene Relevanz):

* Vermeidung von Datenverlust
* Aufrechterhaltung des operationellen Geschäftsablaufs
* Gesetzliche Vorgaben
* Schutz vor Imageverlust
* Vertragsbedingungen

Rechtliche Anforderungen (Ausschnitt):

* Sorgfaltspflicht
* Aufbewahrungspflicht
* Bundesdatenschutzgesetz
* Fernmeldegeheimnis

Richtlinien anhand des IT-Grundschutz-Katalogs des BSI (Bundesamt für Sicherheit).  
https://www.bsi.bund.de/DE/Themen/ITGrundschutz/itgrundschutz_node.html

Beteiligte Personen

* Systemadministratoren
* Sicherheitsbeauftragte
* Sicherheitsinspektoren
* Programmierer
* Anwender
* Servicetechniker (intern und extern)

Gefahren entstehen durch verschiedene Ursachen, beispielsweise höhere Gewalt (Unwetter), technisches Versagen, 
organisatorische Fehler (fehlendes Sicherheitskonzept), menschliches Versagen (versehentlich) oder absichtliche Manipulation (intern und extern).

Organisatorische Fehler umfassen Fehler im Ablauf der EDV des Unternehmens, fehlende Sicherheitskonzepte, oder Probleme bei der Vergabe von Berechtigungen.
Gefahren aus dieser Kategorie ermöglichen Gefahren in anderen Kategorien.

Menschliche Fehlhandlungen entstehen (im Gegensatz zu vorsätzlichen Handlungen) unabsichtlich. 
Beispiele hierfür wären versehentliches Ändern / Löschen von Dateien,
Senden von E-Mails an falsche Empfänger, oder schlechten Umgang mit Kennwörtern.

Die hierzu entgegenstehenden vorsätzliche Handlungen können von externen und internen Personen vorgenommen werden.
Autorisierte Personen können ihre Rechte missbrauchen, Angreifer können versuchen, unautorisierten Zugriff zu erlangen.

## Sicherheitsmanagement

Regelung der
* Gesamtverantwortung für IT-Sicherheit
* Sicherheitsziele
* Ressourcenbereitstellung
* ...

### Klassifikation von Schwachstellen

|   | Ebene           | Inhalt                            | Beispiel                            | Stelle              |
|---|-----------------|-----------------------------------|-------------------------------------|---------------------|
| 5 | Semantik        | Schutz vor Betrug                 | Phishing                            | Fachabteilung       |
| 4 | Logik           | Absicherung von Prozessen         | Benutzer-Lock-out                   | Fachabteilung       |
| 3 | Implementierung | Vermeiden von Programmierfehlern  | SQL-Injcetion, Cross Site Scripting | Entwickler          |
| 2 | Technologie     | Wahl und Einsatz der Technologie  | Verschlüsselung                     | Entwickler, Betrieb |
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

Anschließend (Itarativ):
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

Ein Datenschutzbeauftragter wird benötigt, wenn mindestens 10 Personen im Unternehmen mit der Verarbeitung personenbezogener Daten beschäftigt sind.
Öffentliche Stellen haben immer einen Datenschutzbeauftragten anzustellen. Dieser benötigt technische, organisatorische und juristische Kenntnisse.

### Sicherheitsmanagement

Auf einen Teil des gesamten Risikopotentials werden Schuztmaßnahmen angewandt. Ein weiterer Teil wird durch Versicherungen abgedeckt, 
dies bietet sich vor allem bei Risiken mit geringer Eintrittswahrscheinlichkeit und hohem Schaden an.

### Methodik nach IT-Grundschutz

```
TODO
```

## Maßnahmen

Hauptanforderungen sind die Forderungen nach Wirksamkeit, Wirtschaftlichkeit, Einfachheit und Sicherheit. Diese sollen durch organisatorische, technische, sowie personelle Maßnahmen erreicht werden.

Organisatorische Maßnahmen werden grundsätzlich durch ein Sicherheitskonzept geregelt, welches vom Sicherheitsbeauftragten erstellt wird.
Dieses bestimmt verschiedene Richtlinien:
* Anforderungen an Kennwörter
* Rechte / Benutzergruppen
* Notfallsystem
* Kryptosystem

Technische Maßnahmen beinhalten Maßnahmen zur Erhaltung der Verfügbarkeit, zum Einsatz von Firewalls, sowie Intrusion Detection Systeme.

Personelle Maßnahmen umfassen die Sensibilisierung von Nutzern, beispielsweise zum Sperren von PCs. 
Dies wird durch Schulungen erreicht, Stichwort: "Awareness".

Man unterscheidet allgemein zwischen drei Varianten:

* Präventiv: Einschränkung / Vermeidung von Gefahren im Vorfeld.
* Überwachend: Erkennung von Angriffen bei deren Eintritt. Dies ist rechtlich heikel, momentan besteht der Lösungsansatz in der Speicherung von Überwachungsdaten, welche aber nur in konkreten Angriffsfällen gelesen werden dürfen.
* Reaktiv: Reaktion auf Angriffe zur Verringerung von Schaden, sofortige Gegenmaßnahmen.

Die Maßnahmen können bewertet werden, indem die Wirkung, Kosten, Kombination mit anderen Maßnahmen, sowie Benutzerfreundlichkeit bewertet wird.

Die Dokumentation der Sicherheitsstrategie für alle Mitarbeiter findet in verständlicher Form in den IT-Sicherheitsrichtlinien statt.

```
Inhalte- TODO
```
