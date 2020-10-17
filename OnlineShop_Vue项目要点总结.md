# OnlineShop Vue项目要点总结
***2019.11.03 20:50 Leon***

[项目Github地址](https://github.com/Danjame/VueProjects/tree/master/vue_shop_online) 。

###侦听属性 Watch
1. 深度监听对象:
```
obj: {
     hanlder: function(){
          do something...
     },
     deep: true
}
```
2. 侦听对象属性:
```
'obj.key': function(){
     do something...
}
```

### 事件修饰符
1. 使用 @click.stop 来阻止事件冒泡。
2. 使用 @click.prevent 来阻止事件的默认行为。

### 状态管理模式 Vuex
我把vuex看作vue的前端数据库，在vue的任何一个组件里的数据可以放进vuex里，而其他任何组件可以直接从vuex里获取其他组件存放的数据。所有的公用数据放在vuex的state对象里，通过dispatch和commit分别调用actions和mutations的方法来存放数据，但是实际上我们可以跳过actions直接使用commit调用mutation来存放数据。

### Vue Router
个人更加偏向于使用编程式导航:
1. 其可以更好地帮助你根据不同的条件跳转到不同的地址。
2. 在跳转之前可以先进行某些条件的判断，当条件满足再进行跳转，否则不跳转。
3. 可以在页面跳转时进行其他操作。