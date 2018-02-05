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
