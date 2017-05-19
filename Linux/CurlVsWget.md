# Gemeinsamkeiten und Unterschieden von Curl und wget

## Gemeinsamkeiten

* Command-Line-Tools zum Downloaden über FTP, HTTP and HTTPS
* Senden von POST Requests
* Unterstützen HTTP Cookies
* So erstellt, dass sie ohne User-Interaktion funktionieren (für Skripte)
* Open Source & kostenlos
* Unterstützen Metalink

## Unterschiede

curl

* Curl wird mit libcurl betrieben, einer Cross-Platform Library mit einer stabilen API, die von jedem verwendet werden kann.
* Curl unterstützt mehr Protokolle: FTP, FTPS, HTTP, HTTPS, SCP, SFTP, TFTP, TELNET, DICT, LDAP, LDAPS, FILE, POP3, IMAP, SMTP, RTMP and RTSP
* Curl unterstützt mehr SSL-Libraries
* Curl unterstützt mehr HTTP-Authentifikationsmethoden

wget

* Die große Stärke von wget ist die Fähigkeit, rekursiv zu downloaden, beispielsweise alle Abhängigkeiten einer HTML-Seite.
  * wget -r URL

### Referenz

https://daniel.haxx.se/docs/curl-vs-wget.html
