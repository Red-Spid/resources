# **Boolean** 
> 用于转换一个不是 Boolean 类型的值转换为 Boolean 类型值 (true 或者false)

## **对象属性**

### **constructor**
> 返回对创建此对象的 Boolean 函数的引用
~~~js
var myvar = new Boolean(1);
myvar.constructor;//function Boolean() { [native code] }
~~~

### **protoType**
> 使您有能力向对象添加属性和方法
~~~js
Boolean.prototype.myColor=function()
{
    if (this.valueOf()==true)
    {
        this.color="green";
    }
    else
    {
        this.color="red";
    }
}
var a=new Boolean(1);
a.myColor();
var b=a.color;//green
~~~

## **对象方法**

### **toString()**
> 把布尔值转换为字符串，并返回结果
~~~js
var bool = new Boolean(1);
var myvar = bool.toString();// true
~~~

### **valueOf()**
> 返回 Boolean 对象的原始值。
~~~js
var bool = new Boolean(0);
var myvar = bool.valueOf();//false
~~~

# **Date 对象**
> Date 对象用于处理日期与时间,创建 Date 对象： new Date()

## **以下四种方法同样可以创建 Date 对象**
~~~js
var d = new Date();
var d = new Date(milliseconds);
var d = new Date(dateString);
var d = new Date(year, month, day, hours, minutes, seconds, milliseconds);
~~~
## **Date 对象属性**

### **constructor**
>返回对创建此对象的 Date 函数的引用

~~~js
myDate.constructor;//function Date() { [native code] }
~~~

### **prototype**
>返回对创建此对象的 Date 函数的引用

~~~js
Date.prototype.myMet=function(){
    if (this.getMonth()==0){this.myProp="January"};
    if (this.getMonth()==1){this.myProp="February"};
    if (this.getMonth()==2){this.myProp="March"};
    if (this.getMonth()==3){this.myProp="April"};
    if (this.getMonth()==4){this.myProp="May"};
    if (this.getMonth()==5){this.myProp="June"};
    if (this.getMonth()==6){this.myProp="July"};
    if (this.getMonth()==7){this.myProp="August"};
    if (this.getMonth()==8){this.myProp="Spetember"};
    if (this.getMonth()==9){this.myProp="October"};
    if (this.getMonth()==10){this.myProp="November"};
    if (this.getMonth()==11){this.myProp="December"};
}
var d = new Date();
d.myMet();
// 或者
var d = new Date(); 
d.myMet();
var monthname = d.myProp;
~~~

## **Date 对象方法**

### **getDate()**
> 从 Date 对象返回一个月中的某一天 (1 ~ 31)

~~~js
var d = new Date();
d.getDate();
~~~

### **getDay()**
> 从 Date 对象返回一周中的某一天 (0 ~ 6)

~~~js
var d = new Date();
d.getDay();
~~~

### **getFullYear()**
>从 Date 对象以四位数字返回年份

~~~js
var d = new Date().getFullYear();
// 也可以指定时间
var d = new Date("July 21, 1983 01:15:00").getFullYear();
~~~

### **getHours()**
>返回 Date 对象的小时 (0 ~ 23)

~~~js
var d = new Date().getHours();
// 也可以指定时间
var d = new Date("July 21, 1983 01:15:00").getHours();
~~~

### **getMilliseconds()**
>返回 Date 对象的毫秒(0 ~ 999)

~~~js
var d = new Date().getMilliseconds();
~~~

### **getMinutes()**
>返回 Date 对象的分钟 (0 ~ 59)

~~~js
var d = new Date().getMinutes();
~~~

### **getMonth()**
>从 Date 对象返回月份 (0 ~ 11)

~~~js
var d = new Date().getMonth();
~~~

### **getSeconds()**
>返回 Date 对象的秒数 (0 ~ 59)

~~~js
var d = new Date().getSeconds();
~~~

### **getTime()**
>返回 1970 年 1 月 1 日至今的毫秒数

~~~js
var d = new Date().getTime();
~~~

### **getTimezoneOffset()**
>返回本地时间与格林威治标准时间 (GMT) 的分钟差

~~~js
var d = new Date().getTimezoneOffset();
~~~

### **getUTCDate()**
>根据世界时从 Date 对象返回月中的一天 (1 ~ 31)

~~~js
var d = new Date().getUTCDate();
~~~

### **getUTCDay()**
>根据世界时从 Date 对象返回周中的一天 (0 ~ 6)。

~~~js
var d = new Date().getUTCDay();
~~~

### **getUTCFullYear()**
>根据世界时从 Date 对象返回四位数的年份

~~~js
var d = new Date().getUTCFullYear();
~~~

### **getUTCHours()**
>根据世界时返回 Date 对象的小时 (0 ~ 23)

~~~js
var d = new Date().getUTCHours();
~~~

### **getUTCMilliseconds()**
>根据世界时返回 Date 对象的毫秒(0 ~ 999)

~~~js
var d = new Date().getUTCMilliseconds();
~~~

### **getUTCMinutes()**
>根据世界时返回 Date 对象的分钟 (0 ~ 59)

~~~js
var d = new Date().getUTCMinutes();
~~~

### **getUTCMonth()**
>根据世界时从 Date 对象返回月份 (0 ~ 11)

~~~js
var d = new Date().getUTCMonth();
~~~

### **getUTCSeconds()**
>根据世界时返回 Date 对象的秒钟 (0 ~ 59)

~~~js
var d = new Date().getUTCSeconds();
~~~

### **parse()**
>返回1970年1月1日午夜到指定日期（字符串）的毫秒数

~~~js
var d = Date.parse("March 21, 2022");
~~~

### **setDate()**
>设置 Date 对象中月的某一天 (1 ~ 31)

~~~js
var d = new Date().setDate(15);
//Tue Mar 15 2022 11:58:36 GMT+0800 (中国标准时间)
~~~

### **setFullYear()**
>设置 Date 对象中的年份（四位数字）

~~~js
var d = new Date().setFullYear(15);
~~~

### **setHours()**
>设置 Date 对象中的小时 (0 ~ 23)

~~~js
var d = new Date().setHours(15);
~~~

### **setMilliseconds()**
>设置 Date 对象中的毫秒 (0 ~ 999)

~~~js
var d = new Date().setMilliseconds(300);
~~~

### **setMinutes()**
>设置 Date 对象中的分钟 (0 ~ 59)

~~~js
var d = new Date().setMinutes(30);
~~~

### **setMonth()**
>设置 Date 对象中月份 (0 ~ 11)

~~~js
var d = new Date().setMonth(30);
~~~

### **setMonth()**
>设置 Date 对象中月份 (0 ~ 11)

~~~js
var d = new Date().setMonth(30);
~~~

### **接下来的都一下把 get 换乘 set 就是设置了**

### **toDateString()**
>把 Date 对象的日期部分转换为字符串

~~~js
var d = new Date().toDateString();
~~~

### **toISOString()**
>使用 ISO 标准返回字符串的日期格式

~~~js
var d = new Date().toISOString();
//2022-03-01T04:05:41.934Z
~~~

### **toJSON()**
>以 JSON 数据格式返回日期字符串

~~~js
var d = new Date().toJSON();
//2022-03-01T04:06:33.692Z
~~~

### **toLocaleDateString()**
>根据本地时间格式，把 Date 对象的日期部分转换为字符串

~~~js
var d = new Date().toLocaleDateString();
//2022/3/1
~~~

### **toLocaleTimeString()**
>根据本地时间格式，把 Date 对象的时间部分转换为字符串

~~~js
var d = new Date().toLocaleTimeString();
//下午12:08:02
~~~

### **toLocaleString()**
>根据本地时间格式，把 Date 对象转换为字符串

~~~js
var d = new Date().toLocaleString();
//2022/3/1 下午12:08:39
~~~

### **toString()**
>把 Date 对象转换为字符串

~~~js
var d = new Date().toString();
// Tue Mar 01 2022 12:09:18 GMT+0800 (中国标准时间)

var d = new Date().toTimeString();
//12:09:30 GMT+0800 (中国标准时间)
//把 Date 对象的时间部分转换为字符串。

var d = new Date().toUTCString();
//根据世界时，把 Date 对象转换为字符串。
//Tue, 01 Mar 2022 04:10:05 GMT
~~~

### **UTC()**
>根据世界时返回 1970 年 1 月 1 日 到指定日期的毫秒数

~~~js
var d = new Date().UTC();
//1333065600000
~~~

### **UTC()**
>返回 Date 对象的原始值

~~~js
var d = new Date().valueOf();
//1646107907149
~~~
