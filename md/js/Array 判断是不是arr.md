Array 判断是不是arr

# instanceof 操作符

~~~js
let arr = [];
arr instanceof Array// true
~~~

# constructor 构造器

~~~js
let arr = [];
arr.constructor === Array// true
~~~

# isPrototypeOf   Array原型链上

~~~js
let arr = [];
Array.prototype.isPrototypeOf(arr) // ture
~~~

# Object.getPrototypeOf

~~~js
let arr = [];
Object.getPrototypeOf(arr) === Array.prototype // ture
~~~

# Object.prototype.toString

~~~js
let arr = [];
Object.prototype.toString.call(arr) === '[object Array]' // ture
~~~

# Array.isArray

~~~js
let arr = [];
Array.isArray(arr)
~~~



