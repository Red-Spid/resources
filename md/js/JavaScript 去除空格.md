## **JavaScript数组去除空值**

> 循环检测去空值

~~~js
/**
 * 扩展Array方法, 去除数组中空白数据
 */
Array.prototype.notempty = function() {
    var arr = [];
    this.map(function(val, index) {
        //过滤规则为，不为空串、不为null、不为undefined，也可自行修改
        if (val !== "" && val != undefined) {
            arr.push(val);
        }
    });
    return arr;
}
//调用方法
var a = [1, 2, undefined, 4, "", 5, null, 7, 0, 8];
var b = a.notempty();
//输出b    [1, 2, 4, 5, 7, 0, 8]
~~~

~~~js
//js 数组过滤空值（undefined、null、""、0、false、NaN）
const arr = [undefined, null, "", 0, false, NaN, 1, 2].filter(Boolean);
~~~

> 推荐使用第二种方法

## **JavaScript 去除空格**

> js自带的方法 trim()

~~~js
var str = " 6 6 ";
var str_1 = str.trim();
console.log(str_1); //6 6//输出左右侧均无空格
~~~



> 利用正则匹配替换

~~~js
var str = " 6 6 ";
var str_1 = str.replace(/\s*/g,"");
console.log(str_1); //66
~~~

~~~js
var str = " 6 6 ";
var str_1 = str.replace(/^\s*|\s*$/g,"");
console.log(str_1); //6 6//输出左右侧均无空格
~~~

~~~js
var str = " 6 6 ";
var str_1 = str.replace(/^\s*/,"");
console.log(str_1); //6 6 //输出右侧有空格左侧无空格
~~~

~~~js
var str = " 6 6 ";
var str_1 = str.replace(/(\s*$)/g,"");
console.log(str_1); // 6 6//输出左侧有空格右侧无空格
~~~

