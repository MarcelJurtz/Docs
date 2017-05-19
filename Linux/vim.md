# Vim

[Guide](https://getintodevops.com/blog/how-the-hell-do-i-exit-a-beginners-guide-to-vim)

## Einführung

Einige der Befehle im folgenden Guidebeginnen mit einem Doppelpunkt.  
Der Doppelpunkt initialisiert den Command-Mode und zeigt die Kommandozeile an,
in der der folgende Befehl geschrieben wird.

Befehle ohne Doppelpunkt sind eher vergleichbar mit Hotkeys - diese werden im Default-Mode verwendet. Vim wird in diesem Modus gestartet.

Im folgenden bezeichnen alle groß geschriebenen Befehle spezifische Keys auf der Tastatur.

Alle Befehle sind case-sensitiv.

## Grundlagen

Starten von vim: ```vim```  
Schließen von vim (verwerfen von Änderungen): ```:q!```
Speichern und Schließen: ```:wq```

Bewegen in der geöffneten Datei: ```h```,```j```,```k```,```l```  
Navigation zum Ende des nächsten Worts: ```e```  
Navigation zum Beginn des nächsten Worts: ```w```  
Navigation zum Beginn des letzten Worts ```b```  
Navigation zum Ende der Zeile ```$```  
Navigation zum Beginn einer Zeile ```0```  
Navigation zum Ende einer Datei ```G```  
Navigation zum Beginn einer Datei ```gg```  
Bewegen zu spezieller Zeile (z.B. 285): ```:285```  
Suche nach einem Wort: ```/wort```  

## Insert-Mode

Insert-Mode starten (an aktueller Cursorposition): ```i```  
Insert-Mode beenden: ```ESC```  
Text anhängen: ```A```  

## Visual-Mode

Visual-Mode starten: ```v```  
Visual-Mode beenden: ```ESC```  
Auswahl von Text: ```h```,```j```,```k```,```l```  

## Copy & Paste

Auswahl kopieren:  ```y```  
Auswahl löschen: ```d```  
Zeile kopieren: ```yy```  
3 Zeilen (inkl. aktueller) kopieren: ```3yy```  
Zeile ausschneiden: ```dd```    
5 Zeilen (inkl. aktueller) ausschneiden: ```5dd```  
Einfügen nach aktueller Zeile: ```p```  
Einfügen vor aktueller Zeile: ```P```

## Undo & Redo

Letzte Änderung rückgängig machen: ```u```  
Zuletzt rückgängig gemachte Änderung wiederholen: ```CTRL + R```  
Anzahl an Änderungen anzeigen: ```:undolist```  
Letzte 4 Änderungen rückgängig machen: ```4u```

## Dateien verwalten

index.html öffnen: ```:edit index.html```  
Speichern: ```:w```  
Datei mit anderem Namen speichern: ```:w changes.txt```

## Suchen und ersetzen

TODO

## Syntax-Highlighting

Syntax-Highlighting aktivieren: ```:syntax on```  
Automatische Einrückung aktivieren: ```:set autoindent```  
Einrückung vergrößern: Auswahl im Visual-Mode, ```>```

## Multitasking

Datei als Tab öffnen: ```:tabe server.py```  
Tab nach rechts wechseln: ```:tabn```  
Tab nach links wechseln: ```:tabp```  

Ein Tab wird wir gewohnt mit ```:q!``` oder ```:wq``` geschlossen.

Datei in vertikaler Split-View öffnen: ```:vs index.html```  
Datei in horizontaler Split-View öffnen: ```:sp index.html```  

Wechsel zwischen Split-Views: ```CTRL + W + Pfeiltasten```

## Weiterführende Links

* [Dalibor Nasevic's 12 intermediate/advanced Vim tips](http://dalibornasevic.com/posts/43-12-vim-tips)
* [The official Vim wiki's Best Vim Tips](http://vim.wikia.com/wiki/Best_Vim_Tips)
* [Zzapper's huge list of Vim tips](http://zzapper.co.uk/vimtips.html)
