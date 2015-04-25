# BoughJS

## Как начать

Для начала просто подключите bough-min.js к вашему проекту:
````js
<script src = 'bough-min.js'></script>
````
Далее создайте сцену: 
````js
var scene = new BOUGH.Scene();
scene.position = {x: 250, y: 250};
````
Теперь нужно создать объект:
````js
var rect = BOUGH.createObject();
rect.pos = {x: 100, y: 100, z: 0};
rect.color = '#f00';
rect.draw = function() {
	ctx.fillStyle = this.color;
	ctx.fillRect(this.vx, this.vy, 5, 5);
}
````
и добавить его на сцену:
````js
scene.add(rect);
````
