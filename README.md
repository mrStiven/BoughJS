# BoughJS

## Как начать

Для начала просто подключите bough-min.js к вашему проекту:
````js
<script src = 'bough-min.js'></script>
````
Создайте Canvas и функцию для перерисовки экрана:
````js
var display = {
	width: window.innerWidth,
	height: window.innerHeight,
};

var ctx = cnv.getContext('2d');
ctx.canvas.width = display.width;
ctx.canvas.height = display.height;

reqAniFrame = (function() {
	return window.requestAnimationFrame ||
		window.webkitRequestAnimationFrame ||
		window.mozRequestAnimationFrame ||
		window.oRequestAnimationFrame ||
		window.msRequestAnimationFrame
})();

function loop() {
	reqAniFrame(loop);
}
loop();
````

Далее создайте сцену: 
````js
var scene = new BOUGH.Scene();
scene.position = {x: 250, y: 250};
````

Теперь нужно создать объект и указать его координаты:
````js
var rect = BOUGH.createObject();
rect.pos = {x: 100, y: 100, z: 0};
````

Данный объект мы можем расширить собственными свойставми и методами:
````js
rect.pos = {x: 100, y: 100, z: 0};
rect.color = '#f00';
rect.draw = function() {
	ctx.fillStyle = this.color;
	ctx.fillRect(this.vx, this.vy, 5, 5);
}
````

Теперь добавим его на сцену:
````js
scene.add(rect);
````
