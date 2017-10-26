# Enumerationen

Stellt einen eigenen Datentyp dar und dient der besseren Lesbarkeit anstelle von z.B. numerischen Werten.

```CSharp
Issue s = new Issue();
SetIssueType(IssueType.Bug);


enum IssueType : byte {
	Enhancement = 0,
	Bug = 1,
	FeatureRequest = 2,
	Other = 3
}

private void SetIssueType(IssueType issueType) {
	s.IssueType = issueType;
}
```