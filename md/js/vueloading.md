# 面试题

## vue路由传参有几种方式

> 携带参数跳转
~~~js
 this.$router.push({
    path: `/particulars/${id}`,
})
~~~

> 携带参数跳转
~~~js
 this.$router.push({
    path: `/particulars`,
    params:{
        id:id
    }
})
~~~

> 携带参数跳转 这个会拼到？
~~~js
 this.$router.push({
    path: `/particulars`,
    query:{
        id:id
    }
})
~~~

## vue通信方式

> props 和 $emit() 父组件向子组件传递数据是通过props传递的，子组件传递给父组件是通过$emit触发事件来做到的

> $parent 和 $children 获取单签组件的父组件和当前组件的子组件

> $attrs 和 $listeners A -> B -> C。Vue2.4开始提供了$attrs和$listeners来解决这个问题

> $refs 获取组件实例

> envetBus 兄弟组件数据传递，这种情况下可以使用事件总线的方式

## keep-alive
> keep-alive 是 Vue 内置的一个组件，可以实现组件缓存，当组件切换时不会对当前组件进行卸载。常用的两个属性 include/exclude，允许组件有条件的进行缓存。两个生命周期 activated/deactivated，用来得知当前组件是否处理活跃状态。