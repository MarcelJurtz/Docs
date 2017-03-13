# Generics

Generische Methoden sind mit Typparametern gekennzeichnete Methoden.

```Csharp
class Animal
{
    public string Name { get; set; }
    public Animal(string name = "No Name")
    {
      Name = name;
    }
}
```

## Generic Collections

Generische Collections sind typsicher und performanter als nicht-generische Collections.  
Eine generische Collection erhält den Datentyp bei der Deklaration.

```Csharp
// Liste mit Objekten vom Typ 'Animal'
List<Animal> animals = new List<Animal>();

// Liste mit Standardtypen
List<int> ints = new List<int>();

// Wert hinzufügen
animals.Add(new Animal());
animals.Add(new Animal("Archimonde"));
animals.Add(new Animal() { Name = "Medivh" });

// Wert an bestimmter Position hinzufügen
animals.Insert(1, new Animal("Korialstrasz"));

// Wert entfernen
animals.RemoveAt(1);

// Anzahl an Elementen
Console.WriteLine("Elements: " + animals.Count());

// Foreach
foreach(Animal a in animals)
{
    Console.WriteLine(a.Name);
}
```

Neben der List<> können diverse andere Collection-Arten verwendet werden:
* Stack<T>
* Queue<T>
* Dictionary<TKey,TValue>


## Generische Methoden

Die folgende generische Methode besitzt zwei Parameter. Vorraussetzung ist lediglich,
dass die Parameter vom gleichen Typ sind wie das T im Aufruf.

```Csharp

public static void GetSum<T>(ref T num1, ref T num2)
{
  double dX = Convert.ToDouble(num1);
  double dY = Convert.ToDouble(num2);

  double res = dX + dY;
  Console.WriteLine(num1 + " + " + num2 + " = " + res);
}

// Aufruf
int x = 7, y = 12;
string strX = "7", strY = "12";
GetSum(ref x, ref y);        // 7 + 12 = 19
GetSum(ref strX, ref strY);  // 7 + 12 = 19

```

## Generische Strukturen

```Csharp

public struct Rectangle<T>
{
    private T width;
    private T height;

    public T Width
    {
      get { return width; }
      set { width = value; }
    }

    public T Height
    {
      get { return height; }
      set { height = value; }
    }

    public Rectangle(T w, T h)
    {
      width = w;
      height = h;
    }

    public bool isSquare()
    {
      return Convert.ToDouble(width) == Convert.ToDouble(height);
    }
}


Rectangle<int> rect1 = new Rectangle<int>(42, 11);
Console.WriteLine(rect1.isSquare()); // False

Rectangle<double> rect2 = new Rectangle<double>(3.1415, 3.1415);
Console.WriteLine(rect2.isSquare()); // True

```
