# JavaScript 复习
***2019.10.16 01:22 Leon***

### 移动端 Touch 事件
1. Touch 屏幕触摸事件: touchstart, touchmove, touchend
2. Touch 事件的触发会产生对象数组: touches, changedTouches, targetTouches
3. 通过 event.touches[0], event.changedTouches[0], event.targetTouches[0] 可以获取触点对象。
4. 触点对象包含的常用属性: screenX, screenY, clientX, clientY, pageX, pageY, target
元素id直接获取 DOM

***做增删改查Demo的时候发现, 元素的id名直接就变成了全局变量，不需要通过方法来获取。问了别人，有人说是H5的新规范，有人说是一种BUG。如果说这是一种新规范，那么这种新规范的缺点就太明显了，因为全局变量或者对象就不能和元素id同名了，否则会造成混乱。***

### Apply 与 Call
1. 同: 两者都是用于改变this的指向，也是函数的调用方式，如果没有传入参数或者传入null，那么this的指向将会是默认的window。
2. 异: Apply传入的函数参数是一个参数组，而Call传入的函数参数是相互独立的参数。