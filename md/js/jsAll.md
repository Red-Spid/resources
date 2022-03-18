# **JavaScript 全局函数**
> JavaScript 全局属性和方法可用于创建Javascript对象

## **JavaScript 全局属性**

### **Infinity**
> 代表正的无穷大的数值
> 在Javascript中，超出 1.7976931348623157E+103088 的数值即为Infinity，小于 -1.7976931348623157E+103088 的数值为无穷小
~~~js
var x=1.7976931348623157E+10308;//Infinity
var y=-1.7976931348623157E+10308;//-Infinity
~~~

### **NaN**
> 指示某个值是不是数字值
> 请使用 isNaN() 来判断一个值是否是数字。原因是 NaN 与所有值都不相等，包括它自己

### **Undefined**
> 指示未定义的值
~~~js
var t2;// undefined
~~~

## **JavaScript 全局函数**

### **encodeURI()**
> 把字符串编码为 URI
~~~js
var uri="my test.php?name=ståle&car=saab";
encodeURI(uri)//my%20test.php?name=st%C3%A5le&car=saab
~~~

### **decodeURI()**
> 解码某个编码的 URI
~~~js
var uri="my test.php?name=ståle&car=saab";
encodeURI(uri)//my%20test.php?name=st%C3%A5le&car=saab
decodeURI(uri)//my test.php?name=ståle&car=saab
~~~

### **encodeURIComponent()**
> 把字符串编码为 URI 组件
~~~js
var uri="https://www.123.com/my test.php?name=ståle&car=saab";
encodeURIComponent(uri)//https%3A%2F%2Fwww.runoob.com%2Fmy%20test.php%3Fname%3Dst%C3%A5le%26car%3Dsaab
decodeURIComponent(uri)//https://www.123.com/my test.php?name=ståle&car=saab
~~~

### **decodeURIComponent()**
> 解码一个编码的 URI 组件
~~~js
var uri="https://www.123.com/my test.php?name=ståle&car=saab";
encodeURIComponent(uri)//https%3A%2F%2Fwww.runoob.com%2Fmy%20test.php%3Fname%3Dst%C3%A5le%26car%3Dsaab
decodeURIComponent(uri)//https://www.123.com/my test.php?name=ståle&car=saab
~~~

### **unescape()**
> 对由 escape() 编码的字符串进行解码。
~~~js
unescape( escape("Need tips? Visit ") )
~~~

### **escape()**
> 对字符串进行编码.尽量不要使用该方法可以使用 encodeURI 或 encodeURIComponent 代替。
~~~js
escape("Need tips? Visit ")
//Need%20tips%3F%20Visit%20
~~~

### **eval()**
> 计算 JavaScript 字符串，并把它作为脚本代码来执行
~~~js
eval("2+2")//4
eval("x=10;y=20;");
x*y//200
eval(x+17)//27
~~~

### **isFinite()**
> 检查某个值是否为有穷大的数
~~~js
isFinite(Infinity);  // false
isFinite(NaN);       // false
isFinite(-Infinity); // false

isFinite(0);         // true
isFinite(2e64);      // true, 在更强壮的 Number.isFinite(null) 中将会得到false
 
isFinite("0");       // true, 在更强壮的 Number.isFinite('0') 中将会得到false
~~~

### **isNaN()**
> 检查某个值是否是数字
~~~js
isNaN("2005/12/12")// true
isNaN("Hello")// true

isNaN(0)// fasle
isNaN(-1.23)// fasle
isNaN(5-2)// fasle
isNaN(123)// fasle
~~~

### **Number()**
> 把对象的值转换为数字
~~~js
Number("9999 888") //NaN
Number(new Date) //1646626135300
Number(false) //0
Number(true) //1
~~~

### **Parselnt()**
> 解析一个字符串并返回一个整数
1. 如果 string 以 "0x" 开头，parseInt() 会把 string 的其余部分解析为十六进制的整数
2. 如果 string 以 0 开头，那么 ECMAScript v3 允许 parseInt() 的一个实现把其后的字符解析为八进制或十六进制的数字
3. 如果 string 以 1 ~ 9 的数字开头，parseInt() 将把它解析为十进制的整数
~~~js
parseInt("10")//10
parseInt("10.3")//10
parseInt("22 10 10")//22
parseInt(" 1 ")//1
parseInt("40 years ")//40
parseInt("He was 1")//NaN

parseInt("10",10)//10
parseInt("010")//10
parseInt("10",1)//1
parseInt("0x10")//16
parseInt("10",16)//16
~~~
>**注意：**旧浏览器由于使用旧版本的ECMAScript（ECMAScript版本小于ECMAScript 5，当字符串以"0"开头时默认使用八进制，ECMAScript 5使用的是十进制），所以在解析("010") 将输出8。

### **paseFloat()**
> 解析一个字符串并返回一个浮点数

~~~js
parseFloat("10")//10
parseFloat("10.33")//10.33
parseFloat("10 33")//10
parseFloat(" 10 ")//10
parseFloat("aaa 10 ")//NaN
~~~

### **String()**
> 把对象的值转换为字符串

~~~js

String(new Boolean(1));//true
String(new Boolean(0));//false
String(new Boolean(true));//true
String(new Boolean(false));//false
String(new Date);//返回时间
String(new String("999 888"));// 999 888
String(12345);//12345
~~~