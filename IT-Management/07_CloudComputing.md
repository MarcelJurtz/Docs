# Cloud Computing

Idee der Cloud: dynamisch skalierbare IT-Ressourcen, die flexibel als Dienste über Internettechnologien bereitgestellt und genutzt werden.

* Bei steigendem Bedarf: mehr Ressourcen anmieten
* Bei sinkendem Bedarf: Ressourcen abmieten

Cloud Computing bildet den Weg zu zentralisierten Architekturen, die flexibel eingesetzt werden können unter Nutung eines variablen Kostenmodells, einfacher Integrierbarkeit, direkte Unterstützung der Unternehmensdynamik.

## Definitorische Abgrenzung

*IT aus der Steckdose*

Definition (BITKOM):

* Form der bedarfsgerechten und flexiblen Nutzung von IT-Leistungen
* IT-Leistung kann dabei Anwendung, Plattformen oder Basisinfrastruktur sein.
* wird als Service über das Internet zur Verfügung gestellt

Gartner: Skalierbarkeit und Flexibilität der Services von besonderer Bedeutung.

Internetnutzung stellt eine Muss-Voraussetzung dar.

## Eigenschaften

* Der Anbieter ist für Betrieb und Wartung zuständig
* Der Kunde mietet nur die Leistung und bezahlt nach Verbrauch
* Cloud Computing ist ein Modell, das es erlaubt, bedarfsgerecht, jederzeit und überall bequem über ein Netz auf einen geteilten Pool von konigurierbaren IT-Ressourcen zuzugreifen.
* Als Ressourcen kommen Netze, Server, Speichersysteme, Anwendungen und Dienste in  Betracht.
* Diese IT-Ressourcen können mit minimalen Verwaltungsaufwand und geriner Interaktion  des Serviceproviders schnell über ein Netz bereitgestellt werden.

**Differenzierung:** Bei Outsourcing werden feste Beträge bezahlt, bei Cloud bedarfsgerecht.

Allgemeine Einsatzbereiche:

* einmalige temporäre Bedürfnisse
* Abwicklung von schwer vorhersagbaren Lastspitzen
* Management saisonaler Nachfrage-Effekte
* Outsourcing von Funktionalitäten und Diensten an Dritte allgemein
* Einstieg in neue Unternehmensfelder oder Märkte durch schnell zur Verfügung stehende Services
* Verringerung von Entwicklungszeiten und für kurzfristig benötigte Ressourcen im Rahmen von IT-Projekten
* IT-Ressourcen für neu gegründete Unternehmen

## Abgrenzung zu anderen Modellen

### Klassisches Hosting

Administration liegt beim Nutzer, bedarfsabhängige Elemente fehlen.

### Grid Computing

liefert Technologie für effiziente, gemeinschaftliche und freie Nutzung gemeinsamer IT-Ressourcen (primär Rechenleistung).

### ASP (Application Service Provider)

Geringer Individualisierungsgrad, ASP ist Bestandteil (Vorläufer) des Cloud-Computings.

## Entwicklung, Einordnung und grundlegende Techniken

Entwicklungsschritte:

* Enorme Steigerung der Rechenleistung
* Flächendeckende Verfügbarkeit hoher Bandbreiten
* Virtualisierungstechnologien: bessere, dynamische Ressourcennutzung möglich

Für höherwertige Cloudservices: SOA (Service oriented Architecture)

## Eigenschaften und Merkmale

* On-demand self-service
  * Einfaches Umbuchen, je nach aktuellen Anforderungen
* Broad network access (Breitband-Netzwerk-Zugang)
* Resssource pooling:
  * Multi-tenant-Modelle mit Pool, der Nutzern dynamisch zugewiesen werden kann
  * Alternativ: Single-tenant, jeder Nutzer verfügt über eigene
    * Anwendungen und Daten
    * Betriebssystem
    * Hardware-Infrastruktur
* Rapid elasticity: Elastizität und Skalierbarkeit
* Measured service: Messbare Dienstqualität

## Arten von Cloud Computing

| Merkmal            | IaaS                                                            | PaaS               | SaaS               |
|--------------------|-----------------------------------------------------------------|--------------------|--------------------|
| Abstraktionsgrad   | Sehr niedrig                                                    | Mittel             | Sehr hoch          |
| Verwaltungsaufwand | Hoch                                                            | Mittel             | Niedrig            |
| Anpassbarkeit      | Sehr hoch                                                       | Hoch               | Sehr gering        |
| Zielgruppe         | <ul><li>Systemhäuser</li><li>IT-Dienstleister</li><li>IT-Abteilungen</li><li>Softwareentwickler</li></ul> | Softwareentwickler | Endanwender        |
| Abrechnung         | Verbrauchsabhängig                                              | Verbrauchsabhängig | Verbrauchsabhängig |

### Software as a Service SaaS

* Geschäftsprozesse
* Branchenanwendungen
* CRM, ERP, HR

Anwendungen werden als Services angeboten.
* Administration und Wartung der Anwendung liegt beim Provider
* Abrechnung erfolgt verbrauchsabhängig: Bsp. Anzahl der Nutzer
* Anwendungen laufen als IT-Services auf der Cloud-Infrastruktur des Anbieters
* Keine Clientseitige Installtion der Anwendung beim Nutzer notwendig
* SaaS-Anwednungen müssen nur auf dem Webserver aktualisiert werden.
* Anwendungsbereich: Endanwender

Anbieter:

* Microsoft
* Google
* IBM
* Salesforce
* ...

### Platform as a Service PaaS

* Laufzeitumgebung
* Datenbank
* Entwicklungstools
* Middleware

Plattformen mit einer vollständigen Betriebs- und Entwicklungsumgebung für die Softwareentwicklung. Dabei ist kein Zugriff auf das darunterliegende Betriebssystem möglich.

Komponenten eines Entwicklungsprojekts als fertige Services: z.B. Security-Konzept.

* Anwendungsbereich: Softwareanbieter, Softwareentwickler

Anbieter:

* Windows Azure
* Amazon Web Services
* Google Apps

### Infrastructure as a Service IaaS

* Server
* Speicher
* Rechenleistung

Bereitstellung von IT-Infrastruktur-Komponenten als abstrakte, virtualisierte Services. Der Cloud-Anbieter kümmert sich um die Lastverteilung und stellt die Verfügbarkeit sicher. Dies ermöglicht höchste Flexibilität, erfordert aber auch den höchsten Administrationsaufwand.

* Anwendungsbereich: beispielsweise SQL- Server
* Abrechnung: Genutzes GB je Zelleinheit, Datentransfervolumen etc.

Anbieter:

* IBM
* ...

### XaaS

*Everything as a Service*

* Komplettleistung im Cloud-Computing-Bereich
* Zusätzliche Schicht: Humans as a Service (HuaaS)
* Neu: Mobile Applikationen

## Liefermodelle

### Public Cloud

Inhalte sind öffentlich zugänglich.

Anbieter und potenzieller Nutzer befinden sich nicht in der selben organisatorischen Einheit.

* Benutzer können meist über Web-Portal ihre gewünschten Leistungen spezifizieren
* Nutzer greifen mittels Web-Technologien über das Internet auf IT-Ressourcen zu und teilen sich gemeinsam diese IT-Architektur
* In diesem Cloud-Modell werden hochstandardisierte Geschäftsprozess-, Anwendungs- oder Infrastruktur-Services angeboten.
* Eine individuelle Anpassung, insbesondere bei Anwednungen, ist in der Regel aufwändig und kostspielig (siehe Aufteilung Single-tenant und multi-tenant).


### Private Cloud

Verfügbarkeit besteht nur für ein Unternehmen und vom Unternehmen selbst, Abteilungen können sich Ressourcen selbst zuteilen.

Anbieter und potenzielle Nutzer befinden sich in derselben organisatorischen Einheit.

* Vorteil: Sicherheit
* Werkzeuge der Public-Cloud können auch in der Private Cloud genutzt werden.
* Dies ermöglicht einen eventuellen Wechsel des Liefer-Modells.
* Self-hosting durch das Unternehmen, ausschließlich Mitarbeitern und ausgewählten Partnern des Unternehmens bereitgestellt.
* Ziel: Bessere Auslastung der IT-Infrastruktur
* Managed Private Cloud: Verwaltung durch einen externen IT-Dienstleister

### Hybrid Cloud

Kombination aus private und public Cloud (Nutzung beider Modelle).

* Bestimmte Funktionalitäten in die Public Cloud auslagern und regulärer Betrieb über die Private Cloud
* Wird genutzt um unkritische Anwendungen, Daten oder IT-Ressourcen auszulagern und gleichzeitig geschäftskritische Bereiche weiterhin intern zu lassen.
* Public Cloud zur Behandlung von Last-Spitzen

### Community Cloud

* Gemeinsame Nutzung von IT-Infrastruktur durch mehrere Institutionen
* Betrieb erfolgt entweder durch eine dieser Institutionen oder durch einen Dritten.
* Die Benutzergruppen dieses Cloud-Modells teilen ein gleiches Interesse, beispielsweise Tätigkeit in der gleichen Branche.

## Datenschutz

Gemäß Bundesschutzgesetz ist die Speicherung personenbezogene Daten kritisch.

Bei Verwendung einer private Cloud besteht volle Kontrolle über die eigenen Daten, bei einer public Cloud ist das allerdings nicht gegeben.

Datenverarbeitung nur in EU-Ländern erlaubt, in USA mittels Safe Harbor bzw. Privacy Shield Sonderregelung.

## Sealed Cloud

Ziel: Schaffen einer vertrauenswürdige Plattformen

* Erfüllung entsprechender rechtlicher Anforderungen
* Für die medizinische oder rechtliche Anwendungen (Schweigepglicht)
* Sowohl interne als auch externe Angriffe werden blockiert
* Bsp: Physischer Schutz durch Server hinter Metallkäftig (der sich nur öffnen lässt, wenn die Daten ausgelagert sind)

## Vertragsrechtliche Aspkete

Der Großteil der Leistungen des Cloud-Anbieters ist rechtlich mietvertraglich zu behandeln. In der Regel kommen weitere werkvertragliche oder dienstvertragliche Elemente hinzu.

Der Vertrag mit einem Anbieter besteht in der Regel aus drei Teilen:

* Services, die der Cloud-Anbieter erbringt, Regelungen zur Skalierbarkeit der Dienste, Zusammensetzung der Vergütung
* SLAs
* Regelungen zu den Aspekten Datenschutz + Datensicherheit

Der Vertrag sollte auch Regelungen zu Mängelansprüchen, deren Folgen sowie Haftungsfragen und Haftungsbeschränkungen festlegen.

Außerdem sinnvoll:

* Punkte der Leistungserweiterung und -änderung
* Regelungen zu Streitschlichtungen
* Beendigung und Abwicklung des Vertrags

## Bewertung von Cloud-Computing

| Vorteile                      | Nachteile                       |
|-------------------------------|---------------------------------|
| Flexibilität und Elastizität  | Datensicherheit und Datenschutz |
| Skalierbarkeit                | Verfügbarkeit und Stabilität    |
| Standardisierung              | Rechtliche Hürden               |
| Mobilität                     | Abhängigkeiten                  |
| Backup                        | Kontrollverlust                 |
