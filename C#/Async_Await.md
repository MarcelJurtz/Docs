# Async & Await

Testweise wurde eine einfache grafische Oberfläche mit einem Button und einem Label erstellt.

```csharp
public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            label1.Text = SampleMethod("Marcel");
        }

        private String SampleMethod(String name)
        {
            Thread.Sleep(2000);
            return "Hello, " + name;
        }
    }
```

Bei Klick auf den Button friert die Anwendung nun für die Zeit der Bearbeitung ein,
da die Methode *SampleMethod* auf dem UI-Thread läuft.

Bei CPU-Intensiven Aufgaben besteht dieses Problem häufig, was in einer schlechten User Experience resultiert.

## Task Parallel Library

Gelöst kann das Problem mit Tasks:

```Csharp
// Ersetzen der Zeile *label1.Text = ...*
Task.Factory.StartNew(() => SampleMethod("Marcel")).ContinueWith(t => label1.Text = t.Result);
```

Dieser Code generiert jedoch eine Fehlermeldung aufgrund einer threadübergreifenden Operation.


Der TaskScheduler vermittelt dem Task hierbei, von welchem Context er aufgerufen werdne soll.
Standardmäßig laufen alle Tasks asynchron im Hintergrund, das kann durch den TaskScheduler geändert werden. *FromCurrentSynchronizationContext* verweist hierbei auf den UI-Thread.

```Csharp
Task.Factory.StartNew(() => SampleMethod("Marcel")).ContinueWith(t => label1.Text = t.Result, TaskScheduler.FromCurrentSynchronizationContext());

```

## Async & Await

Async und Await stellen eine Kapselung für die oben dargestellte Schreibweise dar.

Die entsprechende Methode hierfür gibt einen Task zurück, wodurch signalisiert wird, dass auf das Resultat anschließend zugegriffen werden kann. Wann dies geschieht ist jedoch egal.

Beispielsweise liefert eine Methode mit Rückgabewert ```Task<String>``` einen Task zurück, auf dessen String-Wert nach Abschluss zugegriffen werden kann.

Die Angabe des *async* Keywords vor einer Methodenbezeichnung vermittelt dem Compiler und der Runtime, dass der folgende Code ein *await* Keyboard enthalten kann. Es ist jedoch von keiner Funktionalität in dem Sinne.

```Csharp
public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            CallSampleMethod();
            label1.Text = "Waiting...";
        }

        private String SampleMethod(String name)
        {
            Thread.Sleep(2000);
            return "Hello, " + name;
        }

        private Task<String> SampleMethodAsync(String name)
        {
            return Task.Factory.StartNew(() => SampleMethod(name));
        }

        private async void CallSampleMethod()
        {
            var result = await SampleMethodAsync("Marcel");
            label1.Text = result;
        }
    }
```
