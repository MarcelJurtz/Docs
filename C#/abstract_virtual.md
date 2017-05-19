# Abstrakte Klassen & virtuelle Methoden

Mit dem *abstract*-Keyword können Klassen definiert werden, welche nicht instanziiert werden können.

Zusätzlich können abstrakte Methoden erstellt werden. Diese enthalten keinen Methodenrumpf,
und müssen zwingend in erbenden Klassen implementiert werden.

Eine Alternative zu abstrakten Methoden bieten virtuelle Methoden, gekennzeichnet durch das Keyword *virtual*. Diese besitzen einen Methodenrumpf, welcher als Standard-Funktionalität angesehen werden kann. Mit *override* können erbende Klassen diese Methoden überschreiben.

```CSharp
abstract class Shape
{
    public string name { get; set; }

    public virtual void PrintName()
    {
        Console.WriteLine(this.name);
    }

    public abstract double Area();
}
```

Es kann nun keine Instanz von ```Shape``` erstellt werden, jedoch von Klassen, die von Shape erben. Diese können die *PrintName*-Methode von *Shape* nutzen, oder sie überschreiben.  
Jede erbende Klasse muss die Methode *Area* implementieren.

```CSharp
class Rectangle : Shape
{
    double width;
    double height;

    public Rectangle(double width, double height)
    {
        this.width = width;
        this.height = height;
    }

    public override double Area()
    {
        return this.height*this.width;
    }

    public override void PrintName()
    {
        base.PrintName();
        Console.WriteLine("Extra output from Rectangle");
    }
}
```

Der Aufruf kann abschließend beispielsweise so vorgenommen werden:

```CSharp
Rectangle rect = new Rectangle(10, 20);
rect.name = "Rectangle";
Console.WriteLine(rect.Area());
rect.PrintName();

// 200
// Rectangle
// Extra output from Rectangle
```
