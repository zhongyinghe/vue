1、mixin的理解
```
1)mixin会把它的选项内容"混入"组件中
2)在合并应用时除了钩子函数是先后调用关系外，其他的如果是同键名的，则使用组件的
3)全局mixin会影响后面创建的所有实例
```
2、自定义指令
```
自定义指令钩子函数:
    bind:
    inserted:
    update:
    componentUpdated:
    unbind:
```
```
钩子函数参数:
  el:
  binding:
    name
    value
    oldValue
    expression
    arg
    modifiers
  vnode
  oldVnode
```
3、render函数
```
createElement参数
第一个参数:string/Object
第二个参数:如果是属性的，则把属性加入创建的节点中；如果是节点的，则把节点做为创建节点的子节点
第三个参数:虚拟子节点
```
4、插件
```
1、编写插件:
MyPlugin.install = function (Vue, options) {
}

2、使用插件:
Vue.use(MyPlugin)
或者
Vue.use(MyPlugin, { 选项 })
```

5、过滤器<br>
1)局部过滤器
```
filters: {
  capitalize: function (value) {
    if (!value) return ''
    value = value.toString()
    return value.charAt(0).toUpperCase() + value.slice(1)
  }
}
```
2)全局过滤器
```
Vue.filter('cap', function(value, end){
    if (!value) return ''		
    value = value.toString()
    return value.charAt(0).toUpperCase() + value.slice(1) + ' ' + end
})
```
