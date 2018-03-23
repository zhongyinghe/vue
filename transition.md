### transition基础
1、自定义的类
```
v-enter
v-enter-active
v-enter-to

v-leave
v-leave-active
v-leave-to
```
2、自由设定类名
```
enter-class
enter-active-class
enter-to-class

leave-class
leave-active-class
leave-to-class
```
3、钩子函数
```
<transition
  v-on:before-enter="beforeEnter"
  v-on:enter="enter"
  v-on:after-enter="afterEnter"
  v-on:enter-cancelled="enterCancelled"

  v-on:before-leave="beforeLeave"
  v-on:leave="leave"
  v-on:after-leave="afterLeave"
  v-on:leave-cancelled="leaveCancelled"
>
  <!-- ... -->
</transition>
```
4、过渡模式
```
<transition name="fade" mode="out-in">
</transition>
```
5、多元素和多组件间切换
```
<transition>
  <button v-if="isEditing" key="save">
    Save
  </button>
  <button v-else key="edit">
    Edit
  </button>
</transition>
```
```
<transition>
  <button v-bind:key="isEditing">
    {{ isEditing ? 'Save' : 'Edit' }}
  </button>
</transition>
```
```
<transition>
  <button v-bind:key="docState">
    {{ buttonMessage }}
  </button>
</transition>
```
```
<transition name="component-fade" mode="out-in">
  <component v-bind:is="view"></component>
</transition>
```

### 列表过渡
1、进入和离开过渡
```
<transition-group name="list" tag="p">
</transition-group>
```
2、列表的位移过渡
```
<transition-group name="flip-list" tag="ul">
</transition-group>
```
```
.flip-list-move {
  transition: transform 1s;
}
```
### 可复用过渡和动态过渡
1、可复用过渡就是使用组件和slot结合，组件模板就是使用transition标签<br>

2、动态过渡就是通过变量使过渡的进入和离开发生变化

### watch观察状态进行动画
```
A、B变量,watch观察A,computed的内容依赖B;
当watch观察到A变化时，主动地改变B,则computed的内容就会变化
```
