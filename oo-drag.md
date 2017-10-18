```javascript
function Drag(id){
    this.box = document.getElementById(id);
    this.disX = 0;
    this.disY = 0;
}

Drag.prototype.init = function(){
    var _this = this;
    this.box.addEventListener('mousedown',down);
    function down(ev){
        _this.down(ev);
    }
}
//鼠标按下的事件
Drag.prototype.down = function(ev){
    var _this = this;
    this.disX = ev.clientX - this.box.offsetLeft;
    this.disY = ev.clientY - this.box.offsetTop;
    var move = function(ev){
        _this.move(ev);
    }
    var up = function(ev){
        _this.up(ev,move,up);
    }
    document.addEventListener('mousemove',move);
    document.addEventListener('mouseup',up);

    ev.preventDefault();
}
//移动函数
Drag.prototype.move = function(ev){
    this.box.style.left = ev.clientX - this.disX + 'px';
    this.box.style.top = ev.clientY - this.disY + 'px';
}
//鼠标抬起事件
Drag.prototype.up = function(ev,move,up){
    document.removeEventListener('mousemove',move);
    document.removeEventListener('mouseup',up);
}

var d = new Drag('box');

d.init();
```
