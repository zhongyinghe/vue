1、应用理解
```
一个 Vue 应用由一个通过 new Vue 创建的根 Vue 实例和组件树组成.

当创建一个 Vue 实例时，你可以传入一个选项对象

vue是一个响应式系统。当这些属性的值发生改变时，视图将会产生“响应”，即匹配更新为新的值

Object.freeze()，这会阻止修改现有的属性，也意味着响应系统无法再追踪变化。

在Vue实例属性和方法前面要加$,以便与用户定义的属性有所区分,如:
vm.$watch('a', function(newValue, oldValue){
});
```

2、Vue的生命周期
```javascript
new Vue({
    el: '#lifecycle',
    data: {
      a: 1,
    },
    created: function() {
      console.log('a is: ' + this.a);
    },
    beforeMount: function(){
    console.log('this is a beforeMount!');
    },
    mounted: function() {
      console.log('this is a mounted!');
    },
    beforeDestroy: function() {
      console.log('this is a destroyed!');//输不出数据
    }
});
```
3、模板语法<br>
1)原理:
```
Vue 将模板编译为虚拟 DOM 渲染函数。结合响应式系统，在应用程序状态改变时,能重新渲染模板
```
2)简写
```
<!-- 完整语法 -->
<a v-bind:href="url"> ... </a>

<!-- 简写 -->
<a :href="url"> ... </a>
```
```
<!-- 完整语法 -->
<a v-on:click="doSomething"> ... </a>

<!-- 简写 -->
<a @click="doSomething"> ... </a>
```
4、computed属性<br>
1)computed 属性会基于`它所依赖的数据进行缓存`。每个 computed 属性，只有在它所依赖的数据发生变化时，才会重新取值<br>
2)computed和methods的区别:
```
它们的相同点是:都依赖数据的变化而变化
它们的不同点是:computed会缓存数据，多次调用只计算一次,而methods会每次都进行计算
```
3)computed和watch区别
```
B依赖A
computed:A变化了，B自动变化
watch:A变化了，B必须主动设置变化，它才变化
```
4)watch的使用
```
当你需要在数据变化响应时，执行异步操作，或高性能消耗的操作，自定义 watcher 的方式就会很有帮助。
```
这句话不懂。也就是有哪些场景只能用watch,而不能用computed?<br>
猜测:耗时操作就不适合用computed吗?

5、class和style绑定<br>
1)class绑定
```
对象语法:
    a、判断是否为真.如:isActive
    b、外部引用.在data中:判断类名是否为真
    c、compute方式.判断类名是否为真

数组语法:
    a、数组直接对应类名
    b、数组元素判断式
    c、数组+对象判断式
    
组件:
    a、直接赋值
    b、判断式
```
2)style绑定
```
对象语法:
    a、变量对应数据
    b、引用外部变量.样式就在里面
    
数组语法:
    a、每个元素就是一个style
```

6、根据条件进行渲染
```
1)v-if
2)template是无形容器,进行条件分组
3)v-else
4)v-else-if
5)key控制元素不复用.有它则不复用,无它则复用
6)v-show和v-if的区别
    v-show:无论如何都渲染元素;当真时显示元素,当假时隐藏元素(display:one)
    v-if:当真时渲染元素;当假时不渲染元素(这元素根本不存在)
```
