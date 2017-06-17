# HTML

Hypertext Markup Language.

HTML ist eine Textauszeichnungssprache und wird dafür verwendet, Seiten für das WWW zu schreiben.
Gestaltung erfolgt in Kombination mit CSS, Interaktion mit JavaScript.

## Kommentare

```HTML
<!-- HTML-Kommentar -->
```

## Tags

HTML ist in Tags eingeteilt. Damit werden spezielle Textelemente ausgezeichnet.

Beispielhafte HTML-Seite:

```HTML
<!doctype html>
<html>
    <head>
        <title>Titel der Website</title>
    </head>
    <body>
        <h1>Hallo Welt!</h1>
        <a href = "http://www.github.com">Github</a>
        <p>Das ist ein Paragraph.</p>
        <p>Lorem ipsum dolor sit amet, ...</p>
        <ul>
           <li>Item 1 einer nicht-numerierten Liste</li>
           <li>Item 2 einer nicht-numerierten Liste</li>
        </ul>
        <ol>
           <li>Item 1 einer geordneten Liste</li>
           <li>Item 2 einer geordneten Liste</li>
           <ol>
             <li>Item 2.1 einer geschachtelten geordneten Liste</li>
           </ol>
        </ol>
    </body>
</html>
```

Die erste Zeile teilt dem Browser mit, welche HTML-Version verwendet wird (html5 verwendet 'html').
Die Seite selbst wird mit einem ```<html>```-Tag umschlossen.
Alle Inhalte befinden sich innerhalb.

### head

Im ```<head>```-Bereich werden beispielsweise Meta-Informationen oder Stylesheets bzw. Skripte hinterlegt. Das ```<title>```-Tag legt den Titel der Website fest, der in der Tab-Darstellung des Browsers angezeigt wird.

Verwendet werden hier in der Regel title-, script-, link- und meta-tags.

Meta-Tags zur Beschreibung von Inhalten sind folgendermaßen aufgebaut:

```HTML
<meta name="description" content="This is an example website" />
<meta name="keywords" content="website, html, example" />
<meta name="author" content="Marcel" />
```

### body

Im ```<body>```-Bereich finden sich anschließend die eigentlichen Inhalten der Website.

### Text

#### abbr und acronym

```HTML
<abbr title="Hypertext markup language">HTML</abbr>
<acronym title="Hypertext markup language">HTML</acronym>
```

Beim Hover über die jeweilige Abkürzung wird die ausgeschriebene Fassung als Tooltip angezeigt.

#### b und big

Erstellt **fett**, bzw. größer gedruckten Text.  
Big wird in HTML5 **nicht** mehr unterstützt.

#### blockquote

Einrückung, beispielsweise zur Darstellung von Zitaten.

#### br

Generiert einen Zeilenumbruch.

#### center

Zentrierter Text.

#### em und i

*Kursiv* gedrucker Text.

### p

Mit ```<p>``` wird ein einfacher Paragraph gekennzeichnet.  
Manuelle Zeilenumbrüche innerhalb eines Paragraphen können mit ```<br>``` eingefügt werden.

#### q

Zitat, Text wird in Anführungszeichen gestellt.

#### s

Durchgestrichener Text.

#### small

Kleiner Text.

#### strong

Fetter / großer Text.

#### sub

Tiefgestellter Text.

#### sup

Hochgestellter Text.

### hx

Überschriften können folgendermaßen erstellt werden:

```HTML
<h1>Erste Ebene</h1>
<h2>Zweite Ebene</h2>
<h3>Dritte Ebene</h3>
<h4>Vierte Ebene</h4>
<h5>Fünfte Ebene</h5>
<h6>Sechste Ebene</h6>
```

### Bilder

Mit dem ```<img>```-Tag können Bilder eingestellt werden.

```HTML
<img src="link/zum/bild.png">
```


### Listen

#### Definitionslisten

```HTML
<dl>
  <dt>HTML</dt>
  <dd>Is simple</dd>
</dl>
```

#### Ungeordnete Listen

```HTML
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

#### Geordnete Listen

```HTML
<ol>
  <li>Item 1</li>
  <li>Item 2</li>
</ol>
```

### Links

```HTML
<a href="http://www.example.com">Text</a>

<!-- Öffnen in neuem Tab -->
<a href="http://www.example.com" target="_blank">Text</a>

<!-- Öffnen in gleichem Tab (Standard) -->
<a href="http://www.example.com" target="_self">Text</a>

```

### Tabellen

Mit dem Tag ```<table>``` werden Tabellen erzeugt.  
Hierbei gilt folgendes Muster:

```HTML
<table summary="Beispieltabelle">
  <caption>Das ist eine Beispieltabelle</caption>
    <tr> <!-- <tr> für Zeilen -->
        <th>Erster Tabellenkopf</th> <!-- <th> für Tabellenköpfe -->
        <th>Zweiter Tabllenkopf</th>
    </tr>
    <tr>
        <td>Erste Zeile, erste Spalte</td> <!-- <td> für eine Zelle -->
        <td>Erste Zeile, zweite Spalte</td>
    </tr>
    <tr>
        <td>Zweite Zeile, erste Spalte</td>
        <td>Zweite Zeile, zweite Spalte</td>
    </tr>
</table>
```

### Formulare

```HTML
<form action="script.php" method="POST">
  <input type="text" name="txtSample" />
</form>
```

Siehe PHP-Dokumentation.
