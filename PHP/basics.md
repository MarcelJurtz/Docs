# PHP

PHP wird für serverseitige Webanwendungen verwendet und interagiert mit HTML-Formularen.

## HTML-Formulare

```HTML
<form method="POST" action="zieldatei.php">
  <!-- Formularelemente -->
</form>
```

Beim Klick auf den *submit*-Button des Formulars wird die Datei *zieldatei.php* aufgerufen bzw. ausgeführt.

Folgende Formularelemente stehen zur Verfügung (Verwendung bei *type*):

* text (Default)
* password
* checkbox
* radio
* submit
* hidden
* reset
* button (Verwendung mit JavaScript)
* image (Verwendung mit src="")
* file (Verwendung für Dateiupload)

Außerdem stehen die folgenden weiteren Attribute zur Verfügung:

* readonly
* maxlength
* size
* value
* disabled
* tabindex

Die meisten dieser Werte sollten selbsterklärend sein. Einige Ausnahmen werden im Folgenden erklärt.

**Textarea**

Mehrzeilige Eingabefelder werden mit folgendem Schema erzeugt:

```HTML
<textarea rows=X cols=Y>
```

**Radiobuttons**

Gruppierung zusammengehörender Auswahlmöglichkeiten.  
Radiobuttons werden einer Gruppe zugefügt, indem alle gewünschten Radiobuttons den gleichen Namen besitzen. Die Differenzierung erfolgt dann über den Wert (Value).

Vorbelegung mit dem Attribut *checked*.

```HTML
<input type="radio" value="Radiobutton 1" name="rb" checked>
<input type="radio" value="Radiobutton 2" name="rb">
```

**ComboBoxen**

Das Attribut *size* gibt an, wieviele Elemente im zugeklappten Zustand angezeigt werden sollen.  
Mehrfachauswahl wird mit dem Attribut *multiple* erlaubt.
```HTML
<select name="liste" size=1>
  <option>Option 1</option>
  <option>Option 2</option>
  <!-- Vorbelegung -->
  <option selected>Option 3</option>
</select>
```

**Fieldsets**

Mit *Fieldsets* werden Eingabefelder gruppiert.

```HTML
<fieldset>
  <!-- Inputs -->
</fieldset>
```
