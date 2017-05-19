# Interfaces

Interfaces sind Klassen, welche keine Implementierung enthalten, sondern lediglich festlegen,
was ein Element dieses Typs enthalten soll. Eine Klasse, die von einem Interface erbt, muss die Eigenschaften des Interfaces implementieren.

Interfaces werden konventionell mit einem I vor Beginn der eigentlichen Bezeichnung benannt.

```CSharp
interface IDemoInterface
{
  void DoSomething();
}
```

Durch das Interface werden Funktionen definiert, jedoch nicht implementiert.

Eine erbende Klasse verwendet diese wie folgt:

```CSharp
class DemoClass : IDemoInterface
{
  void DoSomething()
  {
    Console.WriteLine("Hello World!");
  }
}
```
