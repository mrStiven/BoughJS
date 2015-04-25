# BoughJS

## Как начать

Для начала просто подключите bough-min.js:
````js
<html>
	<canvas id = 'cnv'></canvas>
	<script src = 'bough-min.js'></script>
	<script>
		var ctx = cnv.getContext('2d');
		var ctx = cnv.getContext('2d');
		ctx.canvas.width = 500;
		ctx.canvas.height = 500;
		
		// exemple
		
	</script>
</html>
````
Создайте сцену, указав ее координаты:
````js

var scene = new BOUGH.Scene();
scene.position = {x: 250, y: 250};
````

Теперь нужно создать объект, указать его координаты и добавить метод draw:
````js
var rect = BOUGH.createObject();
rect.position = {x: 100, y: 100, z: 0};
rect.draw = function() {
	ctx.fillStyle = this.color;
	ctx.fillRect(this.vx, this.vy, 5, 5);
}
````

Далее добавим его на сцену:
````js
scene.add(rect);
````

Ну и в конце надо вызвать метод scene.update() внутри функции перерисовки:
````js
function loop() {
	ctx.clearRect(0, 0, display.width, display.height);
	scene.rotate(0.5);
	
	scene.update();
	requestAnimationFrame(loop);
}
loop();
````

