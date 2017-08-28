# Android Komponenten

Android Anwendungen sind meistens in Java (oder Kotlin) geschrieben.
möglich sind aber auch C/C++ (Spieleentwicklung mit OpenGL) oder Hybrid-Apps mit HTML, CSS und JavaScript.

Komponenten, die in jeder Anwendung vorhanden sind:

* Activities
* Views (Controls)
* Intents

Komponenten, die nicht unbedingt vorhanden sein müssen:

* Services
* Content Provider
* BroadcastReceiver

## Activities

Eine Activity kann sich wie das Android-Pendant zu einer Windows Form oder einer Seite einer Webanwendung vorgestellt werden.
Die Activity stellt einen Ausschnitt des User Interface der Anwendung dar und nimmt meistens einen Großteil des Bildschirms ein (Mit Ausnahme der Statusleiste mit Uhrzeit etc.).

Eine Activity kann einen von vier Zuständen besitzen:

* Running
  * Activity ist sichtbar und bereit für Benutzerinteraktionen
* Paused
  * Activity ist sichtbar, kann aber keine Benutzerinteraktionen empfangen
* Stopped
  * Activity ist nicht sichtbar und kann vom System terminiert werden
* Killed
  * Activity wurde vom System terminiert (Aufruf der finish()-Methode)


Es ist möglich, mit mehreren Activities gleichzeitig zu arbeiten, beispielsweise per Split-Screen-Modus

### Activity Instance State

Der Status einer Activity muss gespeichert werden können, um die Oberfläche auf den Zustand zurücksetzen zu können,
in der ein Anwender sie belassen hat. Zwischen Neustarts der Activity müssen diese Daten übertragen werden.
Beispielsweise Änderung der Ausrichtung (Portrait - Landscape).

### Activity Lifecycle

Siehe https://developer.android.com/reference/android/app/Activity.html:

![Activity Lifecycle](https://developer.android.com/images/activity_lifecycle.png)


## Services

Ein Service ist eine Komponente, die im Hintergrund läuft und ohne User Interface und somit ohne direkte Benutzerinteraktion abläuft.

Services werden für repetitive und potentiell lang laufende Operationen wie Downloads oder Timer, Datenbearbeitung, ... verwendet.

Da ein Service keine grafische Oberfläche besitzt, ist er nicht vom Lifecycle einer Activity abhängig.

Normalerweise läuft ein Service im gleichen Prozess wie der Main Thread der Anwendung, weshalb asynchrone Verarbeitung für Services verwendet werden muss.

### Service Lifecycle

Siehe https://developer.android.com/guide/components/services.html:

![Service Lifecycle](https://developer.android.com/images/service_lifecycle.png)


## Content Providers

Ein Content Provider versorgt eine Anwendung mit Daten einer anderen Anwendung.
Solche Anfragen werden mit der ContentResolver-Klasse behandelt.
Ein Content Provider kann unterschiedliche Möglichkeiten zum Bezug der Daten verwenden
diese Daten können anschließend in einer Datenbank, in Dateien oder über ein Netzwerk gespeichert werden.

Content Provider ermöglichen zentralisierte Speicherung und sind wie eine Datenbank vorstellbar.
Unterstütze Methoden:
* insert()
* update()
* delete()
* query()

Android verwendet häufig die integrierte SQLite Datenbank zur Speicherung.

## Erstellen eines Content Providers

1. Erstellen einer Klasse, die von **ContentProviderbase** erbt
2. Definiere eine URI für den Provider, die dem Zugriff auf den Inhalt dient
3. Erstelle eine eigene SQLite Datenbank
4. Implementiere Queries um verschiedene datenbankspezifische Operationen durchzuführen
5. Registriere den Content Provider in der Activity mittels <provider>-Tag