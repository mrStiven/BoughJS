# BoughJS

## Как начать

Для начала просто подключите bough-min.js:
````js
<script src = 'bough-min.js'></script>
````
Создайте сanvas и сцену, указав ее координаты:
````js

var ctx = cnv.getContext('2d');
ctx.canvas.width = 500;
ctx.canvas.height = 500;

var scene = new BOUGH.Scene();
scene.position = {x: 250, y: 250};
````

Теперь нужно создать объект и указать его координаты:
````js
var rect = BOUGH.createObject();
rect.position = {x: 100, y: 100, z: 0};
````

Далее добавим его на сцену:
````js
scene.add(rect);
````

Ну и в конце надо вызвать метод scene.update() внутри функции перерисовки:
````js
function loop() {
	ctx.clearRect(0, 0, display.width, display.height);
	scene.update();
	
	requestAnimationFrame(loop);
}
loop();
````
Также можно покрутить сцену:
````js
scene.rotate(0.5);
````

