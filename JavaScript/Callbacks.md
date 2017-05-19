# Javascript Event Callbacks

Beispielprojekt:  
Klick auf Button soll Änderungen in Canvas-Element auslösen.

```Javascript
function setup() {
  createCanvas(400,400);
  var button = createButton("Buttontext");
  button.mousePressed(changeColor;
}

function changeColor() {
  bgColor = color(random(255));
}

// 'Callback' für Button
function mousePressed() {
  changeColor();
}

function draw() {
  background(bgColor);
}
```
