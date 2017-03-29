# Electron

Electron basiert auf Chromium, V8 und Node JS

## Warum Desktop?

Browser sind durch Sicherheitsmechanismen sehr abgegrenzt zu anderen Ressourcen.
Zugriff auf Hardware aber notwendig.

## Warum mit Electron?

HTMl, CSS und Javascript Kenntnisse verwenden,
Electron Framework nicht sehr komplex.
Cross Platform Development ohne große Schwierigkeiten.
Keine Latenzzeiten bei Übertragung zu lokaler Datenbank.
Chromium liefert alle Development-Tools.

## Vorgehensweise:

1. Intialisieren
  * npm init
  * electron-prebuilt installieren
  * npm install electron-prebuilt global
2. Configure
  * JSON-Datei zur Konfiguration,
  * main: Start-JS
3. electron-Objekte beziehen
  * const electron = require('electron');
  * const{app} = electron;
  * const{BrowserWindow} = electron;

```JavaScript
let win; // Toplevel-Referenz des Fensters, um Garbage Collection zu verhindern

function createWindow() {
    // Browserfenster erstellen
    win = new BrowserWindow({width: 800, height: 600});
    // index.html der Seite laden
    win.loadURL('file://${__dirname}/index.html');
    // DevTools öffnen
    win.webContents.openDevTools();

    win.on('closed',() => {win = null;});
}

app.on('ready',createWindow);

app.on('window-all-closed', () => {
    // Mac OS X: Anwendung nur explizit beenden
    if(process.platform !== 'darwin') {
        app.quit();
    }
})
```

Es kann ein beliebiges App-Framework verwendet werden, beispielsweise AngularJS, Ember, Redux & React, ...
Für die UI können ebenfalls verschiedene Frameworks verwendet werden, wie z.B. Bootstrap, React Desktop, ...
