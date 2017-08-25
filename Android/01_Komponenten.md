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
