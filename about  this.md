```javascript
/*this:
    window
    事件触发元素
    对象
    undefined*/

//当遇到ES6的箭头函数
/*
   箭头函数:
        var fn2 = () => 10;

        var fn2 = (a,b) => a+b;

        var fn2 = (a,b) => {
            return a+b;
        };

    this永远（一辈子）跟父级走。

箭头函数的拖拽
class Drag {
    constructor(id){
        this.disX = 0;
        this.disY = 0;
        this.box = document.getElementById(id);
        this.box.addEventListener('mousedown',(ev)=>{
            this.down(ev);
        });
    }
    
    down(ev){
        this.disX = ev.clientX - this.box.offsetLeft;
        this.disY = ev.clientY - this.box.offsetTop;
        var move = (ev) => {
            this.move(ev);
        }
        var up = (ev) => {
            this.up(ev,move,up);
        }
        document.addEventListener('mousemove',move);
        document.addEventListener('mouseup',up);
    }
    move(ev){
        this.box.style.left = ev.clientX - this.disX + 'px';
        this.box.style.top = ev.clientY - this.disY + 'px';
    }
    up(ev,move,up){
        document.removeEventListener('mousemove',move);
        document.removeEventListener('mouseup',up);
    }
}
    
    var d = new Drag('box');



*/


```