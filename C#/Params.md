# Params

```CSharp

Console.WriteLine("1 + 2 + 3 = {0}", GetSum(1,2,3));

private double GetSum(params double[] numbers) {
	double sum = 0;
	foreach(int i in nums) {
		sum += i;
	}
	return sum;
}
```

## Named Parameters

```CSharp
PrintFullName(lastname: "Mustermann", firstname: "Max");

private void PrintFullName(string firstname, string lastname) {
	Console.WriteLine("Hello {0} {1}!", firstname, lastname);
}
```