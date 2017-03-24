# JS - Snippets

## Trennzeichen

Einfügen von Trennzeichen in variablen Abständen.

```JavaScript
function delimeter(number, gap)
var num = number.toString();
var newString = "";
var increment = 0;
for(var i = num.length-1; i >= 0; i--) {
  increment++;
  if(increment%gap == 0 && i != 0) {
  	newString = "." + num[i] + newString;
  } else {
  	newString = num[i] + newString;
  }
}

return newString;
```

Anwendung:

```JavaScript
var x = 1234567;
console.log(delimeter(x,3)); // 1.234.567
```
