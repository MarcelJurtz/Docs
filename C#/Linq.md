# LINQ

[Youtube](https://www.youtube.com/watch?v=gwD9awr3NNo)  
[Sourcecode](http://www.newthinktank.com/2017/02/c-tutorial-15/)

Language integrated query.

## Verwendung mit String-Arrays

```Csharp
string[] elems = {
  "Archimonde",
  "Kil'jaeden",
  "Mannoroth",
  "Ner'zhul",
  "Sargeras",
  "Balnazzar",
  "Magtheridon",
  "Mal'Ganis",
  "Tichondrius",
  "Varimathras",
  "Azgalor",
  "Hakkar" };

  // Sucht Elemente mit ' und sortiert diese in umgekehrter alphabetischer Reihenfolge
var elemsSpaces = from elem in elems
                  where elem.Contains("'")
                  orderby elem descending
                  select elem;

foreach(var i in elemsSpaces)
{
    Console.WriteLine(i);
}
// Ner'zhul, Mal'Ganis, Kil'jaeden
```

## Verwendung mit int-Arrays

```Csharp

int[] nums = { 1, 3, 8, 2, 10, 13, 37, 42, 15, 12, 21, 6, 4, 9, 31, 35, 23 };

var gt30 = from num in nums
           where num > 30
           orderby num
           select num;

foreach(var i in gt30)
{
    Console.WriteLine(i);
}
// 31, 35, 37, 42
// gt30 ist vom Typ Linq.OrderedEnumerable

// Ergebnis zu Liste konvertieren
var listGt30 = gt30.ToList<int>();

// Ergebnis zu Array konvertieren
var arrayGt30 = gt30.ToArray();
```

## Verwendung mit Objekten

Verwendete Objekte sind Instanzen der folgenden Klasse:

```Csharp

class Guy
{
    public string Name { get; set; }
    public double Weight { get; set; }
    public double Height { get; set; }
    public int GuyID { get; set; }

    public Guy(string name = "No Name", double weight = 0, double height = 0)
    {
        Name = name;
        Weight = weight;
        Height = height;
    }

    public override string ToString()
    {
        return string.Format("{0} weighs {1}lbs and is {2} inches tall",
        Name, Weight, Height);
    }
}

```

Verwendung von LINQ:

```Csharp

Guy[] guys = {
                new Guy("Archimonde",120.5, 2.80),
                new Guy("Mannoroth", 133, 2.10),
                new Guy("Sargeras", 202.8, 3.70)
             };

// Kombination von Abfragen mit && und ||
var selection = from guy in guys
                where (guy.Weight > 130) && (guy.Height > 3)
                // orderby ...
                select guy;

foreach(Guy guy in selection)
{
    Console.WriteLine(guy.Name);
    // Sargeras
}

```

## LINQ Syntax

Neben den oben dargestellten Methoden können verschiedene Zugriffe getätigt werden, ähnlich SQL.

### Select New

Mit *Select New* können eigene Objekte strukturiert werden. Beispielsweise zur Eingrenzung einer Collection von Objekten auf einen Teilbereich der Attribute oder zum Zusammenfassen von Ergebnissen eines Joins.

### Inner Join

Beispiel: Array mit Haustieren & Array mit zugehörigen Besitzern, gekoppelt über "ID"

```Csharp
var innerJoin = from animal in animals
                join owner in owners
                on animal.ID equals ownder.ID
                select new {
                  OwnerName = owner.Name,
                  AnimalName = animal.Name
                };
```

### Group Join

Group Joins ermöglichen verschachtelte Joins, wie im unteren Beispiel verdeutlicht wird.

```Csharp

var groupJoin = from owner in owners
                orderby owner.ID
                join animal in animals on
                owner.ID equals animal.ID
                into ownerGroup
                select new {
                  Owner = owner.name,
                  Animals = from owner2
                            in ownerGroup
                            orderby owner2.Name
                            select owner2
                };

foreach(var ownerGroup in groupJoin)
{
    Console.WriteLine(ownerGroup.Owner);
    foreach(var animal in ownerGroup.Animals)
    {
      Console.WriteLine("* " + animal.Name);
    }
}

```
