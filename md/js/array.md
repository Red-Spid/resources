# **Array数组的方法**

## **数组属性**

1. constructor	返回创建数组对象的原型函数。
2. length	设置或返回数组元素的个数。
3. prototype	允许你向数组对象添加属性或方法。

~~~js
Array.constructor == function Array() { [native code] }
Array.length == 返回数组的长度
Array.prototype.myUcase=function()
{
    for (i=0;i<this.length;i++)
    {
        this[i]=this[i].toUpperCase();
    }
}

function myFunction()
{
	var fruits = ["Banana", "Orange", "Apple", "Mango"];
	fruits.myUcase();
	var x=document.getElementById("demo");
	x.innerHTML=fruits;
}
~~~

## **Array 对象方法**

### **concat()**
>连接两个或更多的数组，并返回结果
~~~js
var hege = ["Cecilie", "Lone"];
var stale = ["Emil", "Tobias", "Linus"];
var kai = ["Robin"];
var children = hege.concat(stale,kai);
// Cecilie,Lone,Emil,Tobias,Linus,Robin
~~~

### **indexOf()**
>搜索数组中的元素，并返回它所在的位置
> 语法 Array.indexOf(searchElement, fromIndex)
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var a = fruits.indexOf("Apple");//2
~~~
### **lastIndexOf()**
>搜索数组中的元素，并返回它最后出现的位置
> 语法 lastIndexOf(searchElement, fromIndex)
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var a = fruits.lastIndexOf("Apple");//2
~~~
### **isArray()**
>判断对象是否为数组
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
Array.isArray(fruits);// true
~~~

### **join()**
>把数组的所有元素放入一个字符串
> 语法 Array.join(separator)
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var energy = fruits.join();//Banana,Orange,Apple,Mango
~~~

### **keys()**
>返回数组的可迭代对象，包含原始数组的键(key)

~~~js
for(let key of ['a', 'b'].keys()){
    console.log(key);
}
// 0
// 1
 
// 数组含空位
console.log([...[,'a'].keys()]); // [0, 1]
~~~

#### **values()**
>遍历键值

~~~js
for(let key of ['a', 'b'].values()){
    console.log(key);
}
// 0
// 1
 
// 数组含空位
console.log([...[,'a'].values()]); // [undefined, "a"]
~~~
### **map()**
>通过指定函数处理数组的每个元素，并返回处理后的数组
> 语法 .map((value, index, array) => {})
~~~js
var numbers = [4, 9, 16, 25];
numbers.map(Math.sqrt);//2,3,4,5
~~~

### **forEach()**
>查找数组中符合条件的元素索引，若有多个符合条件的元素，则返回第一个元素索引
> 语法 .forEach((currentValue, index, array) => {})
~~~js
function(currentValue, index, arr)	
函数参数:
参数	描述
currentValue	必需。当前元素
index	可选。当前元素的索引值。
arr	可选。当前元素所属的数组对象。
~~~

### **pop()**
>删除数组的最后一个元素并返回删除的元素
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.pop();//Banana,Orange,Apple
~~~

### **push()**
>向数组的末尾添加一个或更多元素，并返回新的长度
~~~js
var fruits = ["Banana", "Orange", "Apple"];
fruits.push("1");//Banana,Orange,Apple,1
~~~

### **shift()**
>删除并返回数组的第一个元素
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.shift()//Orange,Apple,Mango
~~~

### **unshify()**
>把数组转换为字符串，并返回结果
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.unshift("Lemon","Pineapple");
//Lemon,Pineapple,Banana,Orange,Apple,Mango
~~~
### **reduce()**
>将数组元素计算为一个值（从左到右）
~~~js
var numbers = [65, 44, 12, 4];
 
function getSum(total, num) {
    return total + num;
}
numbers.reduce(getSum);//125
~~~

### **reduceRight()**
>将数组元素计算为一个值（从右到左）
~~~js
var numbers = [65, 44, 12, 4];
 
function getSum(total, num) {
    return total + num;
}
numbers.reduceRight(getSum);//125
~~~

### **reverse()**
>反转数组的元素顺序
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.reverse();
//Mango,Apple,Orange,Banana
~~~

### **slice()**
>选取数组的一部分，并返回一个新数组
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.slice(1,3)//Orange,Apple
~~~

### **splice()**
>从数组中添加或删除元素
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2,0,"Lemon","Kiwi");//Banana,Orange,Lemon,Kiwi,Apple,Mango
~~~
### **some()**
>检测数组元素中是否有元素符合指定条件
~~~js
var fruits = [1,2,3,4];
fruits.smoe(function( age ){
    return age > 2;
})//true
~~~

### **sort()**
>对数组的元素进行排序
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();//Apple,Banana,Mango,Orange
var points = [40,100,1,5,25,10];
points.sort(function(a,b){return a-b});//1,5,10,25,40,100
~~~

### **toString()**
>把数组转换为字符串，并返回结果
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.toString();//Banana,Orange,Apple,Mango
~~~

### **valueOf()**
>返回数组对象的原始值
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var v=fruits.valueOf();
// Banana,Orange,Apple,Mango
~~~

### **copyWithin()**
>从数组的指定位置拷贝元素到数组的另一个指定位置中。
~~~js
// 参数1：被修改的起始索引
// 参数2：被用来覆盖的数据的起始索引
// 参数3(可选)：被用来覆盖的数据的结束索引，默认为数组末尾
console.log([1, 2, 3, 4].copyWithin(0,2,4)); // [3, 4, 3, 4]
// 参数1为负数表示倒数
console.log([1, 2, 3, 4].copyWithin(-2, 0)); // [1, 2, 1, 2]
console.log([1, 2, ,4].copyWithin(0, 2, 4)); // [, 4, , 4]
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.copyWithin(2, 0);
// Banana,Orange,Banana,Orange
var fruits1 = ["Banana", "Orange", "Apple", "Mango", "Kiwi", "Papaya"];
fruits1.copyWithin(2, 0, 2);
// Banana,Orange,Banana,Orange,Kiwi,Papaya
~~~

### **entries()**
>返回数组的可迭代对象
~~~js
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.entries();
/*
[0, "Banana"]
[1, "Orange"]
[2, "Apple"]
[3, "Mango"]
*/
~~~

### **every()**
>every() 方法使用指定函数检测数组中的所有元素：如果数组中检测到有一个元素不满足，则整个表达式返回 false ，且剩余的元素不会再进行检测。如果所有元素都满足条件，则返回 true
1. every() 不会对空数组进行检测
2. every() 不会改变原始数组
~~~js
var ages = [32, 33, 16, 40];

function checkAdult(age) {
    return age >= 18;
}

function myFunction() {
    document.getElementById("demo").innerHTML = ages.every(checkAdult);
}
~~~

### **fill()**
>用于将一个固定值替换数组的元素。
~~~js
let arr = Array.of(1, 2, 3, 4);
// 参数1：用来填充的值
// 参数2：被填充的起始索引
// 参数3(可选)：被填充的结束索引，默认为数组末尾
arr.fill(0,1,2); // [1, 0, 3, 4]
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.fill("Runoob");
// Runoob,Runoob,Runoob,Runoob
~~~

### **filter()**
>检测数值元素，并返回符合条件所有元素的数组。
~~~js
var ages = [32, 33, 16, 40];

function checkAdult(age) {
    return age >= 18;
}
ages.filter(checkAdult);//32,33,40
~~~

### **find()**
>返回符合传入测试（函数）条件的数组元素。
~~~js
let arr = Array.of(1, 2, 3, 4);
console.log(arr.find(item => item > 2)); // 3
 
// 数组空位处理为 undefined
console.log([, 1].find(n => true)); // undefined
~~~

### **findIndex()**
>查找数组中符合条件的元素索引，若有多个符合条件的元素，则返回第一个元素索引
~~~js
let arr = Array.of(1, 2, 1, 3);
// 参数1：回调函数
// 参数2(可选)：指定回调函数中的 this 值
console.log(arr.findIndex(item => item == 2)); // 1
 
// 数组空位处理为 undefined
console.log([, 1].findIndex(n => true)); //0
~~~
### **Array.of**
> 将参数中所有值作为元素形成数组
~~~js
let Arrayof = Array.of(1,2,3,4,5, function(){}, {1:1} );
console.log( Arrayof );
~~~

### **Array.from**
>Array.from(arrayLike[, mapFn[, thisArg]]);将参数中所有值作为元素形成数组
~~~js
console.log(Array.from(1, 2, 3, 4)); // [1, 2, 3, 4]
 
// 参数值可为不同类型
console.log(Array.from(1, '2', true)); // [1, '2', true]
 
// 参数为空时返回空数组
console.log(Array.from()); // []
~~~
#### **arrayLike**
~~~js
Array.from([1, 2, 3]); // [1, 2, 3]
~~~
#### **mapFn**
~~~js
Array.from([1, 2, 3], (n) => n * 2); // [2, 4, 6]
~~~
#### **thisArg**
~~~js
let map = {
    do: function(n) {
        return n * 2;
    }
}
let arrayLike = [1, 2, 3];
console.log(Array.from(arrayLike, function (n){
    return this.do(n);
}, map)); // [2, 4, 6]
~~~
#### **类数组对象**

>一个类数组对象必须含有 length 属性，且元素属性名必须是数值或者可转换为数值的字符
~~~js
let arr = Array.from({
  0: '1',
  1: '2',
  2: 3,
  length: 3
});
console.log(arr); // ['1', '2', 3]
 
// 没有 length 属性,则返回空数组
let array = Array.from({
  0: '1',
  1: '2',
  2: 3,
});
console.log(array); // []
 
// 元素属性名不为数值且无法转换为数值，返回长度为 length 元素值为 undefined 的数组  
let array1 = Array.from({
  a: 1,
  b: 2,
  length: 2
});
console.log(array1); // [undefined, undefined]
~~~
### **扩展的方法**
#### **includes()**
>数组是否包含指定值！注意：与 Set 和 Map 的 has 方法区分；Set 的 has 方法用于查找值；Map 的 has 方法用于查找键名

~~~js
// 参数1：包含的指定值
[1, 2, 3].includes(1);    // true
 
// 参数2：可选，搜索的起始索引，默认为0
[1, 2, 3].includes(1, 2); // false
 
// NaN 的包含判断
[1, NaN, 3].includes(NaN); // true
~~~

#### **flat()**
>

~~~js
console.log([1 ,[2, 3]].flat()); // [1, 2, 3]
 
// 指定转换的嵌套层数
console.log([1, [2, [3, [4, 5]]]].flat(2)); // [1, 2, 3, [4, 5]]
 
// 不管嵌套多少层
console.log([1, [2, [3, [4, 5]]]].flat(Infinity)); // [1, 2, 3, 4, 5]
 
// 自动跳过空位
console.log([1, [2, , 3]].flat()); // [1, 2, 3]
~~~

#### **flatMap()**
>先对数组中每个元素进行了的处理，再对数组执行 flat() 方法

~~~js
// 参数1：遍历函数，该遍历函数可接受3个参数：当前元素、当前元素索引、原数组
// 参数2：指定遍历函数中 this 的指向
console.log([1, 2, 3].flatMap(n => [n * 2])); // [2, 4, 6]
~~~

#### **复制数组 ... 扩展运算符**

~~~js
let arr = [1, 2],
    arr1 = [...arr];
console.log(arr1); // [1, 2]
 
// 数组含空位
let arr2 = [1, , 3],
    arr3 = [...arr2];
console.log(arr3); [1, undefined, 3]
~~~

### **数组缓冲区**

1. 数组缓冲区是内存中的一段地址
2. 定型数组的基础
3. 实际字节数在创建时确定，之后只可修改其中的数据，不可修改大小。
~~~js
let buffer = new ArrayBuffer(10);
console.log(buffer.byteLength); // 10
// 分割已有数组缓冲区
let buffer1 = new ArrayBuffer(10);
let buffer2 = buffer1.slice(1, 3);
console.log(buffer2.byteLength); // 2
~~~


### **数组属性**

1. 数组缓冲区是内存中的一段地址
2. 定型数组的基础
3. 实际字节数在创建时确定，之后只可修改其中的数据，不可修改大小。
~~~js
let buffer = new ArrayBuffer(10);
console.log(buffer.byteLength); // 10
// 分割已有数组缓冲区
let buffer1 = new ArrayBuffer(10);
let buffer2 = buffer1.slice(1, 3);
console.log(buffer2.byteLength); // 2
~~~~