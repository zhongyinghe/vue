1、组件要点
```
标签、属性、模板、数据
```
2、组件中的data是使用内部数据<br>

3、子组件模板引用父组件数据
```
静态props 如:<blog-post title="My journey with Vue"></blog-post>
动态props 如:<blog-post :title="param"></blog-post> //param具体内容依赖传值
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
8、组件标签间的标签内容处理 => slot
```
单个slot:
        插入全部内容
        备用内容
        
具名slot:
        有名对有名
        无名对无名.若子组件没有无名slot,则父组件中没有名称的标签内容就被丢弃
        注意:slot是有名替换或者无名替换
        
slot-scope  利用子模板属性(静态和动态)
```
9、在component标签下能够切换多个子组件
```
注意v-bind:is = "xxx";这个xxx变量值的变化就是组件的变化

注意全局注册的组件是如何应用在components属性下的

使用<keep-alive>标签包裹<component>标签，可以把挂载过的组件存在内存中
```

10、props的思考
```
子组件模板使用父组件数据
子模板中的属性,而data提供数据
slot中的属性不用定义在props数组中
直接使用data的数据作为标签文本，不用定义在属性中
```

11、编写可复用组件
```
综合应用:props、event和slot
```
12、子组件索引<br>

13、递归组件:注意设定终止条件<br>

14、组件之间的循环引用<br>

### 补充
1)、自定义事件
```
自定义事件的触发不由父组件决定，有子组件决定.它是click的还是change的还是move的，都由子组件决定
```

### 组件理解
```
组件封装可重用代码
组件就是组合在一起使用的元件
所有的vue组件都是Vue实例,接收相同的选项对象，提供相同的生命周期钩子
要确保在vue根实例实例化之前完成组件的注册
父子组件的关系:
  父组件向下传递数据给子组件: props向下
  子组件将自身发生的变化通知到父组件: events向上
  注:props向下是单向数据流,父组件更新数据，子组件自动更新，不要试图修改子组件的prop
```
