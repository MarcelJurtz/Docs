# File - Input/Output

```Csharp
using System.IO;
using System.Text;
```

## Zugriff auf Verzeichnisse

```Csharp
DirectoryInfo current = new DirectoryInfo(".");
DirectoryInfo home = new DirectoryInfo(@"C:\Users\marcel.jurtz");

Console.WriteLine(current.FullName);
// Aktuelles Verzeichnis, Debug-Verzeichnis des Projekts

Console.WriteLine(home.FullName);
// C:\Users\marcel.jurtz

Console.WriteLine(home.Name);
// marcel.jurtz

Console.WriteLine(home.Attributes);
// Directory

Console.WriteLine(home.CreationTime);
// 23.09.2016 07:56:00

DirectoryInfo parent = home.Parent;
// C:\Users
```

## Verzeichnis erstellen

```Csharp

DirectoryInfo newDir = new DirectoryInfo(@"C:\Users\marcel.jurtz\Desktop\NewDir");
Directory.CreateDirectory(newDir.FullName);

```

## Dateien erstellen

```Csharp

string filePath = @"C:\Users\marcel.jurtz\Desktop\NewDir\test.txt";

string[] fileContent = { "Line 1", "Line 2", "Line 3" };
File.WriteAllLines(filePath, fileContent);

```

## Dateien einlesen

```Csharp

foreach(string line in File.ReadAllLines(filePath))
{
    Console.WriteLine(line);
}

```

## Dateien eines Typs beziehen

```Csharp

FileInfo[] txtFiles = newDir.GetFiles("*.txt",SearchOption.AllDirectories);
// AllDirectories: inkludiere Unterverzeichnisse

foreach(FileInfo file in txtFiles)
{
    Console.WriteLine(file.Name);
    // Größe in Bytes:
    Console.WriteLine(file.Length);
}

```

## Filestream

Zugriff auf Dateien mittels Filestream.

```Csharp

// Schreiben
FileStream fs = File.Open(filePath, FileMode.Create);
string str = "Hello World!";
byte[] byteArray = Encoding.Default.GetBytes(str);
fs.Write(byteArray, 0, byteArray.length);

// Lesen
fs.Position = 0;
byte[] newByteArray = new byte[byteArray.length];

for(int i = 0; i < newByteArray.Length; i++)
{
    newByteArray[i] = (byte)fs.ReadByte();
}

Console.WriteLine(Encoding.Default.GetString(newByteArray));

```

## StreamWriter

```Csharp

StreamWriter sw = File.CreateText(filePath);
sw.Write("Hallo ");
sw.WriteLine("Welt!");
sw.WriteLine("Neue Zeile");
sw.Close();

```

## StreamReader

```Csharp

StreamReader sr = File.OpenText(filePath);

// Erste Zeile
Console.WriteLine(sr.ReadLine());

// Reset Position an den Anfang
sr.Position = 0;

// Alles
Console.WriteLine(sr.ReadToEnd());

```

## BinaryWriter

## BinaryReader
