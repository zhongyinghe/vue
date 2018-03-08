1、组件要点
```
标签、属性、模板、数据
```
2、组件中的data是使用内部数据<br>

3、子组件模板引用父组件数据
```
静态props
动态props
```
4、父组件监听子组件触发事件
```
父组件中v-on:xxx="yyy"
在子组件中触发事件,this.$emit('xxx')(可以传值)
```
5、表单输入组件
```
模板:
  value属性对应props:["value"]
  input事件
关系:
  v-model="xxx" 通过xxx变量获取数据
  this.$refs.input.value会影响输入框内容; input是ref="mm"中的mm;value是v-bind:value="vv"中的vv
  this.$emit触发input事件，第二个参数会影响v-model的xxx
```
6、定制组件v-model=>checkbox
```
了解原先的属性和事件(value和oninput)
改属性和事件(在组件的model属性中定义)
在模板中落实改属性
注意原值
```
7、非父子组件通信
```
事件总线中心: var bus = new Vue()
在组件A中触发事件:bus.$emit('xxxx',值)
在组件B中的created钩子函数中监听事件:bus.$on('xxxx', 参数 => {})
```
