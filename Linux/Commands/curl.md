# Curl

Curl (cURL, Client for URLs oder Curl URL Request Library) ist ein Kommandozeilen-Programm zum Übertragen von Dateien in Rechnernetzen.

Curl eignet sich beispielsweise zum Testen von REST-APIs.

```bash
# Lädt den HTML-Quellcode der Website
curl URL
```

## HTTP-Methoden

Z.B. für REST-APIs mit POST / PUT.  
Standardmäßig wird eine GET-Request gesendet.

* Post: curl -d data URL
  * Beispiel: ```curl -d "firstname=Marcel&lastname=Jurtz" http://localhost:8080/test```
* PUT: curl -X PUT -d data URL

## Login

```bash
curl -u username:password url
```

## Download

Beispiel: Bilddatei

```curl URL``` ergibt nur binäre Daten.

```bash
curl -o filename.jpg URL
```
