# Vue.js 入门总结
***2019.10.19 23:58 Leon***

### 环境搭建
去node官网下载安装node.js, node里面已经集成了npm

### 安装
1. npm install vue
2. npm install –global vue-cli
3. vue init webpack my-project

### 项目文件说明
1. Static: 静态资源
2. Node_modeules: 项目依赖的第三方node包
3. Src: 整个项目的源代码
     - Main.js: 项目的入口文件
     - App.vue: 项目的原始根组件
     - Router
     - Components: 项目组件
     - Assets: 图片资源
4. Config: 项目的配置文件
     - Index.js: 基础配置信息
     - Dev.env.js: 开发环境的配置信息
     - Prod.env.js: 线上环境配置信息
5. Build: 项目web-pack的配置内容
     - Webpack.base.conf.js 的resolve对象可定义路径别名
6. Package.json: 项目开发的依赖
7. Package-lock.json: 第三方包的具体版本
8. LICENSE: 开源协议的说明
9. Index.html: 首页默认的模版文件
10. Gitignore: 定义不被提交到git的文件
11. Eslintrc.js: 配置了代码的规范
12. Eslintignore: 配置了不受到Eslinktrc影响到文件
13. Editorconfig: 配置了编辑器的自动化语法
14. Balbelrc: 用于作语法的转换

### 多页应用与单页应用
1. 多页应用：每次页面跳转都会返回一个新的HTML页面，首屏时间快，搜索引擎优化效果好，但是页面切换慢。
2. 单页应用：每次页面跳转都会通过JS动态把当前内容删除，然后再渲染新的DOM结构，页面跳转不需要做HTML请求，减少http发送时延，因此页面切换快，但是首屏时间慢，搜索引擎优化效果差。

### Vue.js知识要点
1. 以vue结尾的都是单文件组件。
2. 双向绑定使用v-model。
3. 路由就是根据不同的网址，返回不同的内容。
4. Tempalte里面只能有一个根标签。
5. Ref用法：标签使用ref绑定DOM, 逻辑里使用this.$refs操作DOM (尽量避免操作DOM)。
6. 父子组件传递数据
     - 父传子：父组件页面的子组件标签上绑定父组件的data里的属性，子组件里使用props来接收该属性。
     - 子传父：子组件里使用this.$emit('event', params)向外触发事件和传递数据，父组件页面的子组件标签上使用@event监听事件并且触发函数，通过函数给data里的属性赋值。
7. 父子组件数据联动: 使用watch监听传送的数据变化。
8. Vuex: vue.js的状态管理库，它采用集中式存储管理应用的所有组件的状态，可以利用vue.js的数据响应机制来进行高效的状态更新。
9. Router-link: 使用属性tag可以改变其默认的a标签。
10. Keep-alive 是一个包裹组件，可以缓存不活动的组件实例，而不销毁它们。而以下两个钩子会在keep-alive树内所有的嵌套组件中触发:
     - Activated: 展示组件实例时触发
     - Deactivated: 跳出组件实例时触发
11. 递归组件：在组件中引用组件自身，把驼峰式命名的组件名字使用"-"拆分作为标签名即可使用递归组件。

12. Transition是个包裹组件，只会把过渡效果应用到其包裹的内容上，不会额外渲染DOM元素，也不会出现在检测过的组件层级中。

13. 其他

设定宽高比的方法：
```
Width: 100%;
Overflow:hidden;
Height: 0;
Padding-bottom: 50%;
```
多余文字显示为省略号的方法：

```
Overflow:hidden;
White-space: nowrap;
Text-overflow: ellipsis;
```