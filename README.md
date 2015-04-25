# BoughJS

## Как начать

Для начала просто подключите bough-min.js к вашему проекту:
````js
<script src = 'bough-min.js'></script>
````
Создайте сanvas и сцену, указав ее координаты:
````js
var display = {
	width: window.innerWidth,
	height: window.innerHeight,
};

var ctx = cnv.getContext('2d');
ctx.canvas.width = display.width;
ctx.canvas.height = display.height;

var scene = new BOUGH.Scene();
scene.position = {x: 250, y: 250};
````

Теперь нужно создать объект и указать его координаты:
````js
var rect = BOUGH.createObject();
rect.pos = {x: 100, y: 100, z: 0};
````

Теперь добавим его на сцену:
````js
scene.add(rect);
````
