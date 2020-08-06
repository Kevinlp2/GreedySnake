#贪吃蛇小游戏

###简单介绍
贪吃蛇小游戏实现思路是以一个正方形的左上角为起始坐标画正方形，
在canvas画布中随机生成食物，蛇身是由几个正方形拼接起来。
键盘的 ↑↓←→ 控制蛇的移动方向

###防抖函数 解决连续多次点击出错

```html
/**
   * 防抖函数 解决连续多次点击出错
   * @param event
   */
  function debounce(event) {
    if(timer){
      clearTimeout(timer)
    }
    timer=setTimeout(()=>{
      // console.log('timer')
      timer=undefined
      let e = event || window.event || arguments.callee.caller.arguments[0];
      if (e && e.keyCode == 40) { //下
        if (direction != 38) direction = 40;
      }else  if (e && e.keyCode == 37) { //左
        if (direction != 39) direction = 37;
      }else if (e && e.keyCode == 39) { //右
        if (direction != 37) direction = 39;
      }
      else if (e && e.keyCode == 38) { // 上
        if (direction != 40) direction = 38;
      }
    },100)
  }
```
