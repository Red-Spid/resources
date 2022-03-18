# **String 对象方法**

> String 对象用于处理文本（字符串）

## **String 对象创建方法： new String()**

~~~js
var txt = new String("string");
// 或者更简单方式
var txt = "string";
~~~

## **String对象属性**

### **constructor**
> 对创建该对象的函数的引用

~~~js
var txt = "Hello World!";
txt.constructor//function String() { [native code] }
~~~

### **length**
> 允许您向对象添加属性和方法

~~~js
var txt = "Hello World!";
txt.length//12
~~~

### **prototype**
> 允许您向对象添加属性和方法

~~~js
function employee(name,jobtitle,born){
    this.name=name;
    this.jobtitle=jobtitle;
    this.born=born;
}
var fred=new employee("Fred Flintstone","Caveman",1970);
employee.prototype.salary=null;
fred.salary=20000;
~~~
## **String对象方法**

### **charAt()**
> 返回在指定位置的字符

~~~js
var str = "HELLO WORLD";
str.charAt(2)// L
~~~

### **charCodeAt()**
> 返回在指定的位置的字符的 Unicode 编码

~~~js
var str = "HELLO WORLD";
str.charCodeAt(0)// 72
~~~

### **concat()**
> 连接两个或更多字符串，并返回新的字符串

~~~js
var str1 = "Hello ";
var str2 = "world!";
var n = str1.concat(str2);// Hello world!
~~~

### **endsWith()**
> 判断当前字符串是否是以指定的子字符串结尾的(区分大小写)

~~~js
let str = "Hello world";
str.endsWith("world")   // 返回 true
str.endsWith("World")   // 返回 false
~~~

### **fromCharCode()**
> 将 Unicode 编码转为字符

~~~js
var n = String.fromCharCode(65);// A
~~~

### **indexOf()**
> 返回某个指定的字符串值在字符串中首次出现的位置

~~~js
var str="Hello world, welcome to the universe.";
var n=str.indexOf("welcome");// 13
~~~

### **includes()**
> 查找字符串中是否包含指定的子字符串

~~~js
var str = "Hello world, welcome to the Runoob。";
var n = str.includes("world");// true
~~~

### **lastIndexOf()**
> 从后向前搜索字符串，并从起始位置（0）开始计算返回字符串最后出现的位置

~~~js
var str="I am from runoob，welcome to runoob site.";
var n=str.lastIndexOf("runoob");// 28
~~~

### **match()**
> 查找找到一个或多个正则表达式的匹配

~~~js
var str="The rain in SPAIN stays mainly in the plain"; 
var n=str.match(/ain/g);// ain,ain,ain
~~~

### **repeat()**
> 复制字符串指定次数，并将它们连接在一起返回

~~~js
var str = "a";
str.repeat(2);// aa
~~~

### **replace()**
> 在字符串中查找匹配的子串，并替换与正则表达式匹配的子串

~~~js
var str="Visit Microsoft! Visit Microsoft!";
var n=str.replace("Microsoft","a");
//Visit a!Visit Microsoft!
~~~

### **replaceAll()**
> 在字符串中查找匹配的子串，并替换与正则表达式匹配的所有子串

~~~js
var str="Visit Microsoft! Visit Microsoft!";
var n=str.replaceAll("Microsoft","a");
//Visit a!Visit a!
~~~

### **search()**
> 查找与正则表达式相匹配的值

~~~js
var str="Visit a!"; 
var n=str.search("a");//6
~~~

### **slice()**
> 提取字符串的片断，并在新的字符串中返回被提取的部分

~~~js
var str="Hello world!";
var n=str.slice(1,5);// ello
~~~

### **split()**
> 把字符串分割为字符串数组

~~~js
var str="How are you doing today?";
var n=str.split(" ");
//How,are,you,doing,today?
~~~

### **startsWith()**
> 查看字符串是否以指定的子字符串开头

~~~js
var str = "Hello world, welcome to the Runoob.";
var n = str.startsWith("Hello");// true
~~~

### **substr()**
> 从起始索引号提取字符串中指定数目的字符

~~~js
var str="Hello world!";
var n=str.substr(2,3)// llo
~~~

### **substring()**
> 提取字符串中两个指定的索引号之间的字符

~~~js
var str="Hello world!";
str.substring(3);// lo world!
str.substring(3,7);// lo w
~~~

### **toLowerCase()**
> 把字符串转换为小写

~~~js
var str="world!";
str.toLowerCase();//world!
~~~

### **toUpperCase()**
> 把字符串转换为大写

~~~js
var str="world!";
str.toUpperCase();//WORD!
~~~

### **trim()**
> 去除字符串两边的空白

~~~js
var str = "       a        ";
alert(str.trim());//a
~~~

### **toUpperCase()**
> 根据本地主机的语言环境把字符串转换为小写

~~~js
var str = "Aa";
var res = str.toLocaleLowerCase();// aa
~~~

### **toLocaleUpperCase()**
> 根据本地主机的语言环境把字符串转换为大写

~~~js
var str = "Aa";
var res = str.toLocaleUpperCase();// AA
~~~

### **valueOf()**
> 返回某个字符串对象的原始值

~~~js
var str="Hello world!";
str.valueOf();// Hello world!
~~~

### **toString()**
> 返回一个字符串

~~~js
var str = "a";
var res = str.toString();// a
~~~

## **String HTML 包装方法**

### **anchor()**

> 创建 HTML 锚
~~~js
var txt="Chapter 10";
txt.anchor("chap10");
alert(txt.anchor("chap10"));
~~~
> **其他的方法**
~~~js
var txt = "Hello World!";
document.write("<p>字体变大: " + txt.big() + "</p>");
document.write("<p>字体缩小: " + txt.small() + "</p>");
document.write("<p>字体加粗: " + txt.bold() + "</p>");
document.write("<p>斜体: " + txt.italics() + "</p>");
document.write("<p>固定定位: " + txt.fixed() + "</p>");
document.write("<p>加删除线: " + txt.strike() + "</p>");
document.write("<p>字体颜色: " + txt.fontcolor("green") + "</p>");
document.write("<p>字体大小: " + txt.fontsize(6) + "</p>");
document.write("<p>下标: " + txt.sub() + "</p>");
document.write("<p>上标: " + txt.sup() + "</p>");
document.write("<p>链接: " + txt.link("http://www.w3cschool.cc") + "</p>");
document.write("<p>闪动文本: " + txt.blink() + " (不能用于IE,Chrome,或者Safari)</p>")
~~~