# CSS

Cascading Style Sheets

Wird zur Gestaltung von HTML verwendet.

## Einbindung

### CSS-Datei

```HTML
<link rel="stylesheet" type="text/css" href="stylesheet.css">
```

### Inline-Styles

Einbindung im head-Bereich der HTML-Seite.

```HTML
<style>
   selector { eigenschaft: wert; }
</style>
```

### Einbindung auf Element-Ebene

````HTML
<div style='eigenschaft: wert;'>
</div>
````

## Syntax

### Kommentare

```CSS
/* CSS Kommentar */
```

### Selektoren

Selektoren zielen auf bestimmte HTML-Elemente (anhand Tag, Klasse, ID, ...)
und weisen diesen Eigenschaften zu.

```CSS
selektor {
  eigenschaft: wert;
  eigenschaft: wert;
  /* beliebig viele weitere Eigenschaften */
}
```

#### Selektion aller Elemente

```CSS
/* Selektion aller Elemente */
* {
  eigenschaft: wert;
}
```

#### Selektion von Klassen

```CSS
/* Selektion der Klasse "klasse" */
.klasse {
  eigenschaft: wert;
}
```

#### Selektion verschachtelter Klassen

```CSS
/* Selektion eines Objekts, das zwei Klassen enthält */
.klasse1.klasse2 {
  eigenschaft: wert;
}
```

#### Selektion von IDs

```CSS
/* Selektion der ID "id" */
#id {
  eigenschaft: wert;
}
```

#### Selektion anhand von Attributen

```CSS
/* Selektion von Elementen mit bestimmten Attributen */
[attr] {
  eigenschaft: wert;
}

/* Selektion von Elementen mit bestimmten Attributwerten */
[attr='wert'] {
  eigenschaft: wert;
}

/* Selektion von Elementen, bei denen ein Attributwert mit etwas festgelegtem beginnt */
[attr^='we'] {
  eigenschaft: wert;
}

/* Selektion von Elementen, bei denen ein Attributwert mit etwas festgelegtem endet */
[attr$='rt'] {
  eigenschaft: wert;
}

/* Selektion von Elementen, bei denen ein Attributwert etwas bestimmtes enthält */
[attr~='er'] {
  eigenschaft: wert;
}
```

#### Vererbung

```CSS
/* Selektion eines direkten Kind-Elements*/
.elternteil > .kindelement {
  eigenschaft: wert;
}

/* Selektion aller Kinder (auch von "Enkelkindern") */
.elternteil .kindelement {
  eigenschaft: wert;
}
```

#### Selektion von Nachbarn

```CSS
/* Auswahl des direkten Vorgängers */
.klasse-direkt-zuvor + .klasse {
  eigenschaft: wert;
}

/* Auswahl eines beliebigen Vorgängers */
.beliebige-klasse-zuvor ~ .klasse {
  eigenschaft: wert;
}

```

#### Kombination der Selektoren

Alle Selektoren können kombiniert werden.  
Beispiel:

```CSS
div.klasse[attr$='rt'] {
  eigenschaft: wert;
}
```

#### Pseudoklassen

Mit Pseudoklassen können Elemente anhand deren Zustand ausgewählt werden.

```CSS
/* Mauszeiger-Hover */
:hover {
  eigenschaft: wert;
}

/* Besuchter Link */
:visited {
  eigenschaft: wert;
}

/* Unbesuchter Link */
:link {
  eigenschaft: wert;
}

/* Aktuell im Fokus befindliches Eingabeelement */
:focus {
  eigenschaft: wert;
}

```

### Eigenschaften

```CSS
selektor {

    /* Einheiten */
    width: 30%;       /* in Prozent */
    font-size: 2em;   /* mal der derzeitigen Schriftgröße */
    width: 250px;     /* in Pixeln */
    font-size: 12pt;  /* in Punkten */
    width: 42cm;      /* in Zentimetern */
    width: 184mm;     /* in Millimetern */
    width: 5in;       /* in Zoll */

    /* Farben */
    background-color: #ABC                  /* in kurzem Hex */
    background-color: #08B1DA               /* in langem Hex */
    background-color: silver                /* benannte Farbe */
    background-color: rgb(255, 255, 255)    /* in RGB */
    background-color: rgb(10%, 20%, 30%)    /* in RGB Prozent */
    background-color: rgba(255, 0, 0, 0.3); /* in semi-transparentem RGB */

    /* Bilder */
    background-image: url(/pfad/image.jpg);

    /* Schriften */
    font-family: Arial;
    font-family: "Courier New"; /* Anführungszeichen benötigt, wenn Leerzeichen in Namen */
    font-family: "Courier New", Trebuchet, Arial; /* Selektion mit Fallback-Lösungen */
}
```

## Spezifizität

// TODO
