# Exception Handling

```CSharp
double val1 = 5;
double val2 = 0;

try {
	double x = divide(val1, val2);
} catch(System.DivideByZeroException e) {
	Console.WriteLine("Division by zero not allowed.");
} finally {
	// Block will always be accessed after try / catch
	// Use for garbage collection / e.g. closing of database connection
}

private double divide(double valueA, double valueB) {
	if(valueB == 0) {
		throw new System.DivideByZeroException();
	}
	return valueA/valueB;
}
```