vue学习编译逻辑 自定义编译vue

# new Vue 或 createApp({})

- 设计理念由经典MVC模式中，M是指业务模型，V是指用户界面，C则是控制器，使用MVC的目的是将M和V的实现[代码](https://baike.baidu.com/item/代码/86048)分离，从而使同一个程序可以使用不同的表现形式。其中，View的定义比较清晰，就是用户界面。

## 实现data的数据相应

~~~js
 for (let index = 0; index < nodes.length; index++) {
        // const element = nodes[index];
        if (nodes[index].nodeName == "#text") {

            let ret = assignment(nodes[index], 0, e);
            nodes[index].nodeValue = ret;

            // console.log(ret,'-------0')
        } else {
            let ret = assignment(nodes[index], 1, e);
            nodes[index].innerText = ret;
            // console.log(ret,'-------1')

        }
    }
~~~

