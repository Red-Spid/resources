# **Browser 对象**

## **navigator**
> Navigator 对象包含有关浏览器的信息
> **注意：** 没有应用于 navigator 对象的公开标准，不过所有浏览器都支持该对象

### **Navigator 对象属性**

#### **appCodeName**
> 返回浏览器的代码名
~~~js
navigator.appCodeName//'Mozilla'
~~~

#### **appCodeName**
> 返回浏览器的名称
~~~js
navigator.appName//'Netscape'
~~~

#### **appVersion**
> 返回浏览器的平台和版本信息
~~~js
navigator.appVersion//'5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.51 Safari/537.36 Edg/99.0.1150.30'
~~~

#### **cookieEnabled**
> 返回指明浏览器中是否启用 cookie 的布尔值
~~~js
navigator.cookieEnabled//true
~~~

#### **platform**
> 返回运行浏览器的操作系统平台
~~~js
navigator.platform//'Win32'
~~~

#### **userAgent**
> 返回由客户机发送服务器的user-agent 头部的值
~~~js
navigator.userAgent//true
~~~

### **Navigator 对象方法**

#### **javaEnabled()**
>指定是否在浏览器中启用Java
~~~js
navigator.javaEnabled()//false
~~~

#### **taintEnabled()**
>指定是否在浏览器中启用Java
~~~js
navigator.taintEnabled()//false
~~~

## **Screen 对象**
> Screen 对象包含有关客户端显示屏幕的信息
> **注意： **没有应用于 screen 对象的公开标准，不过所有浏览器都支持该对象

### **Screen 对象属性**

#### **availHeight**
> 返回屏幕的高度（不包括Windows任务栏）
~~~js
screen.availHeight//870
~~~

#### **availWidth**
> 返回屏幕的宽度（不包括Windows任务栏）
~~~js
screen.availWidth//1440
~~~

#### **colorDepth**
> 返回目标设备或缓冲器上的调色板的比特深度
~~~js
screen.colorDepth//24
~~~

#### **height**
> 返回屏幕的总高度
~~~js
screen.height//900
~~~

#### **width**
> 返回屏幕的总宽度
~~~js
screen.width//24
~~~

#### **pixelDepth**
> 返回屏幕的颜色分辨率（每象素的位数）
~~~js
screen.pixelDepth//24
~~~

## **History 对象**
> History 对象包含用户（在浏览器窗口中）访问过的 URL
> History 对象是 window 对象的一部分，可通过 window.history 属性对其进行访问
> **注意：** 没有应用于 navigator 对象的公开标准，不过所有浏览器都支持该对象

### **Navigator 对象属性**

### **length**
> 返回历史列表中的网址数
1. **注意：** Internet Explorer和Opera从0开始，而Firefox、Chrome和Safari从1开始。
~~~js
history.length
~~~

### **History 对象方法**

#### **back()**
> 加载 history 列表中的前一个 URL
~~~js
// back() 方法可加载历史列表中的前一个 URL（如果存在）
history.back();
//调用该方法的效果等价于点击后退按钮或调用 history.go(-1)。
~~~

#### **forward()**
> 加载 history 列表中的下一个 URL
~~~js
// back() 方法可加载历史列表中的下一个 URL（如果存在）
history.forward();
//调用该方法的效果等价于点击后退按钮或调用 history.go(1)。
~~~

#### **go()**
> 加载 history 列表中的某个具体页面
~~~js
history.go(number|URL)
~~~

## **Location 对象**
> Location 对象包含有关当前 URL 的信息
> Location 对象是 window 对象的一部分，可通过 window.location.xxx 格式的相关属性对其进行访问
### **Location 对象属性**

#### **hash**
> 返回一个URL的锚部分
~~~js
location.hash// 返回 #后(#en/zh/123)
~~~

#### **host**
> 返回一个URL的主机名和端口
~~~js
location.host// 返回 http://或https://后面fanyi.baidu.com
~~~

#### **hostname**
> 返回URL的主机名
~~~js
location.hostname// 返回 http://或https://后面fanyi.baidu.com
~~~

#### **href**
> 返回完整的URL
~~~js
location.href// https://fanyi.baidu.com/aldtype=16047#en/zh/Browser
~~~

#### **pathname**
> 返回的URL路径名
~~~js
location.pathname
~~~

#### **port**
> 返回一个URL服务器使用的端口号
~~~js
location.port
~~~

#### **protocol**
> 返回一个URL协议
~~~js
location.protocol// http:
~~~

#### **search**
> 返回一个URL的查询部分
~~~js
location.search// '?aldtype=16047'
~~~

### **Location 对象方法**

#### **assign()**
> 载入一个新的文档
~~~js
location.assign(URL)// assign()方法加载一个新的文档
~~~

#### **reload()**
> 重新载入当前文档
~~~js
location.reload()//(true/false)
~~~

#### **replace()**
> 用新的文档替换当前文档
~~~js
location.replace(URL)
~~~

## **JavaScript 存储对象**
> Web 存储 API 提供了 sessionStorage （会话存储） 和 localStorage（本地存储）两个存储对象来对网页的数据进行添加、删除、修改、查询操作
1. localStorage 用于长久保存整个网站的数据，保存的数据没有过期时间，直到手动去除
2. sessionStorage 用于临时保存同一窗口(或标签页)的数据，在关闭窗口或标签页之后将会删除这些数据

### **实例**

~~~js
// 保存数据语法
localStorage.setItem("key", "value");
// 读取数据语法
var lastname = localStorage.getItem("key");
// 删除数据语法
localStorage.removeItem("key");
~~~