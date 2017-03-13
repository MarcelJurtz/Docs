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
