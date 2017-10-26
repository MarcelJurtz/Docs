# Kontrollstrukturen

## Operatoren

* Relationale Operatoren: >, >=, <, <=, ==, !=
* Logische Operatoren: && (AND), || (OR), ! (NOT)

Beim Vergleichen von Werten kann zudem die Art des Vergleichs festgelegt werden.

```CSharp
String val1 = "Hello";
String val2 = "World!";

bool equal = val1.Equals(val2, StringComparison.[...]);
```

## If & Else

```CSharp
if(condition) {
	// Commands
} else if(condition) {
	// Commands
} else {
	// Commands
}
```

## Ternary Operator

Kurzfassung von If/Else zur Zuweisung von Werten.

```CSharp
int age = 20;
bool allowedToDrive = age >= 18 ? true : false;
```

## Switch / Case

```CSharp
int age = 20;
String result;
switch(age) {
	case 1:
	case 2:
		result = "The age is 1 or 2";
		break;
	case 3:
		result = "The age is 4";
		break;
	case 4:
		result = "Blabla";
		break;
	default:
		result = "Anything else goes here";
}
```

## While Schleife

Wiederholen von Befehlen, solang eine Bedingung korrekt ist.

```CSharp
int i = 0;
while(i <= 10) {
	Console.WriteLine(i.ToString());
	i++;
}
```

Mit ```Continue``` und ```Break``` kann die aktuelle Iteration beeinflusst werden. Continue überspringt den Rest der Befehle und fährt mit der folgenden Iteration fort, Break verlässt die Schleife vorzeitig.

## Do-While Schleife

Die Funktion der do-while Schleife ist ähnlich zu der der while Schleife. Der Body der Schleife wird allerdings mindestens ein Mal durchgeführt, da die Prüfung der Bedingung erst am Ende der Schleife stattfindet.

```CSharp
int i = 5;
do {
	Console.WriteLine(i.ToString());
	i++;
} while(i <= 4)
```