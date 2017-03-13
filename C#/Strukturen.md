# Strukturen

Ein struct-Typ ist ein ein Werttyp zur Zusammenfassung kleinerer Gruppen zusammegehöhrender Variablen, z. B. Koordinaten eines Rechtecks oder die Merkmale eines Lagerartikels.

Der Aufbau von Strukturen ähnelt dem von Klassen, jedoch sind folgende Unterschiede zu beachten:

* Strukturen sind Werttypen (Klassen sind Referenztypen).
* Alle Strukturtypen erben implizit von der System.ValueType-Klasse.
* Durch die Zuweisung zu einer Variablen mit dem Strukturtyp wird eine Kopie des zugewiesenen Wertes erstellt.
* Der Standardwert für eine Struktur wird erzeugt, indem für alle Werttypfelder der Standardwert und für alle Verweistypfelder null festgelegt wird.
* Zur Konvertierung zwischen einem Strukturtyp und object werden Boxing- und Unboxingoperationen verwendet.
* Im Kontext von Strukturen hat this eine andere Bedeutung.
* Instanzfelddeklarationen für eine Struktur dürfen keine Variableninitialisierungen enthalten.
* Eine Struktur darf keine parameterlosen Instanzkonstruktoren deklarieren.
* Eine Struktur darf keine Destruktoren deklarieren.


```Csharp

public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  

```

Strukturen sollten wie primitive Datentypen verwendet werden und sich so verhalten, außerdem sollten sie möglichst leichtgewichtig sein um Geschwindigkeitsvorteile wie der Speicherung im Stack statt im Heap zu nutzen.

[MSDN - Struct](https://msdn.microsoft.com/de-de/library/ah19swz4.aspx)  
[MSDN - Unterschiede Klassen / Strukturen](https://msdn.microsoft.com/de-de/library/aa664471(v=vs.71).aspx)
