# PassByValue & PassByReference

Normalerweise werden Argumente einer Methode in Form von "Pass by Value" übergeben.
Änderungen innerhalb der Methode beeinflussen demnach nicht die ursrpüngliche Variable.

```CSharp
int a  = 5;
Console.WriteLine(a.toString()); // 5
increaseA(a);
Console.WriteLine(a.toString()); // 5

private void increaseA(int a) {
	a += 5;
}

```

Variablen können als Output-Variablen definiert werden, wodurch Variablen bearbeitet werden können, die sich außerhalb der Methode befinden.

```CSharp
int a  = 5;
int b;
increaseValue(a, out b);

private void increaseValue(int a, out int b) {
	b = a + 5;
}
```

Alternativ kann auch explizit angegeben werden, dass Argumente nach dem Pass by Reference Prinzip übergeben werden sollen.

```CSharp

int num1 = 13;
int num2 = 42;

Console.WriteLine("Before: Num1 = {0}, Num2 = {1}", num1, num2);
SwitchVals(num1, num2);
Console.WriteLine("After: Num1 = {0}, Num2 = {1}", num1, num2);

private void SwitchVals(ref int val1, ref int val2) {
	int temp = val2;
	val2 = val1;
	val1 = temp;
}

```