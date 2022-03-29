# 生命周期

## new vue()
- init Events & Lifecycle
- 初始化 事件 生命周期

## beforeCreate
- init injections & reactivity
- 创建之前 注射与反应性 还没有data数据

## created
- 创建 这事有data

### 从creatd()钩子函数到beforeMount钩子函数之间称之为编译模板阶段，此时模板编译成功，生成了一个编译好的模板字符串，在内存中将这个模板字符串渲染为内存中的DOM，但是还在内存中，没有挂载到页面中。

## beforeMount
- 可以在渲染前最后一次获取到vue中的数据，

## mounted
- 钩子函数发生在此阶段，此时的vue实例已经被渲染到页面上，用户可以看到vue实例的页面，我们可以操作DOM等

## beforeUpdate
- 更改之前

## updated
- 更改后

### 当用户关闭整个页面或者执行了某些$destroy时，就会从运行阶段进入销毁阶段（主要的一大特点是运行了beforeDestroy钩子函数

## beforeDestroy
- 销毁前执行的钩子函数，可以继续使用vue实例中的数据，如data methods filters，derictives等等。

## destroyed
- vue实例中的数据不可用了。
~~~js
created : 在绑定元素的属性或事件监听器被应用之前调用。
beforeMount : 指令第一次绑定到元素并且在挂载父组件之前调用。。
mounted : 在绑定元素的父组件被挂载后调用。。
beforeUpdate: 在更新包含组件的 VNode 之前调用。。
updated: 在包含组件的 VNode 及其子组件的 VNode 更新后调用。
beforeUnmount: 当指令与在绑定元素父组件卸载之前时，只调用一次。
unmounted: 当指令与元素解除绑定且父组件已卸载时，只调用一次。
~~~
# 基本数据类型 数组/对象(复制/拷贝)
- 基本的数据类型：String, Number, boolean, Null, Undefined,Symbol(ES6新增)
- 对象数据类型(也称为引用数据类型)：Array,Object,Function
~~~js
    /* 
        深层(复制/拷贝)对象
        利用JSON对数据的转换实现
    */
    var a={a:1,b:2};
    var b = JSON.parse( JSON.stringify(a));
    b.a=2;
    console.log(a,b)

    /*
        数组(复制/拷贝)
     如何实现深度拷贝(克隆)
     拷贝的数据里有对象/数组
     拷贝的数据里不能有对象/数组,即使有对象/数组可以继续遍历对象、数组拿到里边每一项值，一直拿到是基本数据类型，然后再去复制，就是深度拷贝。
      */
  
      //知识点储备
     /*
         如何判断数据类型:arr-Array null -Null
         1.typeof返回的数据类型有:String，Number,Boolean,Undefined,Object,Function。
         2.Object.prototype.toString.call(obj)。
     */
     
         let result = 'abcd';
         result = null;
         result = [1,3];
         console.log(Object.prototype.toString.call(result).slice(8,-1)); //[object Array]，sclice截取字符串后:Array(拿到分类)。
         //console.log(typeof Object.prototype.toString.call(result));  //string
     
     
         //for in 循环对象(属性名)、数组(下标)，推荐在循环对象属性的时候，使用for...in,在遍历数组的时候的时候使用for...of。
         //for in 循环遍历对象属性名
         let obj = {username:'zhangsan',age:22};
         for(let i in obj){
             console.log(i);  //username age
         }
     
         //for in 循环遍历数组下标
         let arr = [1,3,'abc'];
         for(let i in arr){        //数组的可以用for of对应数组值
             console.log(i); //0 1 2
         }
     
         //定义检测数据类型的功能函数
         function checkedType(target){
             return Object.prototype.toString.call(target).slice(8,-1);
         }
         console.log(checkedType(result));  //Array
     
         //实现深度克隆--对象/数组
         function clone(target){
             //判断拷贝的数据类型
             //初始化变量的result 成为最终克隆的数据
             let result,targetType = checkedType(target);
             if(targetType === 'Object'){
                 result = {};
             }else if(targetType === 'Array'){
                 result = [];
             }else{
                 return target;   //如果是基本数据类型:(String, Number, boolean, Null, Undefined)就直接反回去。
             }
     
             //遍历目标数据
             for(let i in target){
                //获取遍历数据结构的每一项值。
                 let value = target[i];   //i=1,i=2,i=..
                   //判断目标结构里的每一值是否存在对象/数组
                 if(checkedType(value) === 'Object' || checkedType(value) === 'Array'){ //如果对象OR数组里嵌套了对象/数组
                     //继续遍历获取到的value值
                     result[i] = clone(value);    //这个只执行一次,数组里只有一个对象
                 }else{  //获取到的value值是基本的数据类型或者是函数。
                     result[i] = value;  //因为arr3数组的下标0和1都是Number类型,只有下标2才是Object(转去执行1046行)
                 }
             }
             return result;
         }
         let arr3 = [1,2,{username:'dudu',age:32}];
         let arr4 = clone(arr3);    //相当于复制了一份arr3的基本数据
         console.log(arr4);
         arr4[2].username = 'gate';
         arr4[2].age = 65;
         console.log(arr3,arr4);  //arr3下标2是{username:'dudu':age:32},arr4下标2是{username:gate,age:65}
~~~


# 验证数据类型
~~~js
function checkedType(target){
        return Object.prototype.toString.call(target).slice(8,-1);//[object RegExp]
        //return Object.prototype.toString.apply(target).slice(8,-1);[object RegExp]
        //return Object.prototype.toString.bind(target).slice(8,-1);  toString() { [native code] }
     }
console.log( checkedType( /^1/ ) )
~~~

# css中position
- relative, absolute, fixed,static, inherit, sticky

> static默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right 或者 z-index 声明）。

> relative生成相对定位的元素，相对于其正常位置进行定位。因此，"left:20" 会向元素的 LEFT 位置添加 20 像素。

> absolute 生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。

> fixed生成固定定位的元素，相对于浏览器窗口进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。

> sticky粘性定位，该定位基于用户滚动的位置。它的行为就像 position:relative; 而当页面滚动超出目标区域时，它的表现就像 position:fixed;，它会固定在目标位置。注意: Internet Explorer, Edge 15 及更早 IE 版本不支持 sticky 定位。 Safari 需要使用 -webkit- prefix (查看以下实例)。

> inherit 规定应该从父元素继承 position 属性的值。

## 当需要停止冒泡行为时，可以使用
~~~js
function stopBubble(e) { 
//如果提供了事件对象，则这是一个非IE浏览器 
if ( e && e.stopPropagation ) 
    //因此它支持W3C的stopPropagation()方法 
    e.stopPropagation(); 
else 
    //否则，我们需要使用IE的方式来取消事件冒泡 
    window.event.cancelBubble = true; 
}
~~~
## 当需要阻止默认行为时，可以使用
~~~js
//阻止浏览器的默认行为 
function stopDefault( e ) { 
    //阻止默认浏览器动作(W3C) 
    if ( e && e.preventDefault ) 
        e.preventDefault(); 
    //IE中阻止函数器默认动作的方式 
    else 
        window.event.returnValue = false; 
    return false; 
}
~~~