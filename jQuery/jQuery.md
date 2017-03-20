# jQuery

jQuery ist eine JavaScript-Bibliothek, die dabei hilft, mit weniger Code mehr zu erreichen.
Sie vereinfacht die Schreibweise diverser allgemeiner Aufgaben, beispielsweise AJAX, Event-Handling, etc.

## Einbindung

Die Einbindung erfolgt als Skript:

```HTML
// Einbindung per Web
<script src='https://code.jquery.com/jquery-3.1.0.min.js'></script>

// Einbindung mit lokaler Datei
<script src='js/jquery-3.1.0.min.js'></script>
```

## Selektoren

Selektoren werden verwendet, um auf ein Element zuzugreifen.  
Dies ist auch ohne jQuery möglich und sieht wie folgt aus:

```JavaScript
document.getElementsByClassName('skillset');
```

```JavaScript
// Selektion des gesamten Viewports
var page = $(window);

// Selektion von HTML-Elementen
// und Speichern dieser in Variablen
var paragraph = $('p');       // Selektiert alle <p>
var table1 = $('#table1');    // Selektiert alle Elemente mit der ID 'table1'
var squares = $('.square');   // Selektiert alle Elemente mit der Klasse 'square'
var square_p = $('p.square')  // Selektiert alle parapgraphen mit der Klasse 'square'
```

## Events

jQuery eignet sich sehr gut für die Steuerung von Events.
Eines der meistverwendeten Events hierzu ist *ready* des Dokuments.
Dieses wird getriggert, wenn das Element fertig geladen ist.

```JavaScript
$(document).ready(function(){
  // Dieser Code wird ausgeführt, wenn die Seite fertig geladen ist
});
```

Die Funktion kann auch ausgelagert werden:

```JavaScript
function helloWorld() {
  alert("Hello World!");
}

$(document).ready(helloWorld);
```

Folgende Auflistung enthält die wichtigsten Events:

```JavaScript
$('#cmdDemo').click(hellWorld);       // Klick
$('#cmdDemo').dblclick(helloWorld);   // Doppelklick
$('#cmdDemo').hover(helloWorld);      // Hover
$('#cmdDemo').keydown(helloWorld);    // Wenn Taste gedrückt wird
$('#cmdDemo').keyup(helloWorld);      // Wenn Taste losgelassen wird
$('#cmdDemo').keypress(helloWorld);   // Wenn Taste gedrückt ist
$('#cmdDemo').mousemove(helloWorld);  // Bei Bewegung der Maus
$('#cmdDemo').mouseenter(helloWorld); // Mausposition betritt Element
$('#cmdDemo').mouseleave(helloWorld); // Mausposition verlässt Element

// Formulare
$('#cmdDemo').focus(helloWorld);      // Fokussierung
$('#cmdDemo').blur(helloWorld);       // Fokus entfernt
$('#cmdDemo').submit(helloWorld);     // Submit
$('#cmdDemo').select(helloWorld);     // Selektion eines Elements
```

Alle diese Events können auch ausgelöst werden, hierzu wird die Funktion einfach ohne Parameter aufgerufen.

```JavaScript
$('#cmdDemo').dblclick();
```

Außerdem können mit einem Selektor mehrere Events behandelt werden:

```JavaScript
$('#cmdDemo').on(
  {dblclick: function1}
  {hover: function2}
  {click: function3}
);
```

## Effekte

Mithilfe vorgefertigter Effekt-Funktionen kann beispielsweise
die Sichtbarkeit von Elementen verändert werden.

```JavaScript
// Verstecken eines Elements
$('.tab').hide();

// Aufruf einer Funktion beim Verstecken des Elements
$('.tab').hide(function(){
    // Bei Ausführung dieses Codes ist das Element bereits versteckt
});
```

Die folgende Auflistung stellt einige der Effekte dar:

```JavaScript
var elems = $(.klasse1);
elems.hide();         // Element ausblenden
elems.show();         // Ausgeblendetes Element einblenden
elems.toggle();       // Hide / Show umschalten
elems.fadeOut();      // Langsames Ausblenden
elems.fadeIn();       // Langsames Einblenden
elems.fadeToggle();   // FadeOut / FadeIn umschalten
elems.fadeTo(0.7);    // Transparenz (zwischen 0 und 1)
elems.slideUp();      // Slide nach oben
elems.slideDown();    // Slide nach unten
elems.slideToggle();  // SlideUp / SlideDown umschalten
```

Alle diese Effekte können mit einer Zeitangabe und einer Callback-Funktion aufgerufen werden.  
Die Zeitangabe erfolgt in Millisekunden und legt fest, wie lang der Effekt dauert.

```JavaScript
elems.hide(1200, helloWorld);
```

Eine Ausnahme gibt es bei ```fadeTo()```, hier wird zuerst die Zeitangabe gefordert,
 anschließend die benötigte Transparenz, gefolgt von der Callback-Funktion.


Die Callback-Funktion wird jeweils nach dem Effekt aufgerufen.

## Manipulation

HTML-Elemente können mit jQuery verändert werden,
beispielsweise durch das Zuweisen einer neuen Klasse oder das Entfernen einer anderen.

```JavaScript
$('p').addClass('klasse1'); // Fügt allen <p> die Klasse 'klasse1' hinzu
```

Folgende Auflistung zeigt einige dieser Funktionen:

```JavaScript
$('p').append('Lorem Ipsum');       // Text am Ende anhängen
$('p').text('Lorem Ipsum');         // Text setzen
$('p').attr('class');               // Bezieht Attribut
$('p').attr('class', 'content');    // Setzt Attribut
$('p').hasClass('taming-slim-20');  // true, wenn Element die Klasse besitzt
$('p').height();                    // Bezieht / Setzt die Höhe eines Elements
```

Beim Bezug von Eigenschaften von Elementen mit den oben gezeigten Methoden
wird nur jeweils der Wert des ersten Objekts ermittelt.

Um die Werte von allen Elementen zu beziehen kann wie folgt vorgegangen werden:

```JavaScript
var heights = [];

$('h1').each(function) {
  heights.push($(this).height());
}
```
