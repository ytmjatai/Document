## 概述
公司技术栈开始用vue主导开发，但因为公司前端会vue的不多所以在项目中用到vue的技术不是很深，之前出去面试被接连打击，而且本来打算开始为公司vue的项目构建自己的组件库所以去下载了iview(https://www.iviewui.com/)
的源码(https://github.com/iview/iview)
打算研究一番，学习大神的组件封装模式和vue的深层技术的运用，随便写博客系列来记录下自己的心得，因为是个人总结所以可能在认识会有点局限也欢迎各路大神一起讨论学习。
## iview目录结构

![](https://images2018.cnblogs.com/blog/960483/201805/960483-20180508101510764-203130855.png)

1.assets—图片存放目录<br/>
2.build—Webpack配置存放目录<br/>
3.dist—打包之后页面存放目录<br/>
4.examples—组件的demo页面存放目录<br/>
5.src—组件根目录<br/>
6.components—组件存放目录<br/>
7.directives—组件封装的指令存放目录<br/>
8.locale—组件封装的语言配置存放目录<br/>
9.mixins—组件封装的混入存放目录<br/>
10.styles—组件的样式根目录<br/>
11.animation—动画样式<br/>
12.common—公共样式<br/>
13.components—组件样式<br/>
14.mixins—混入样式<br/>
15.custom.less—样式公共变量<br/>
16.index.less—样式入口<br/>
17.utils—组件内部公共方法<br/>
18.index.js—组件入口
## 源码解析
#### index.js入口
![](https://images2018.cnblogs.com/blog/960483/201805/960483-20180508103955379-1022254739.jpg)
在examples文件中的main.js中加载iview组件
![](https://images2018.cnblogs.com/blog/960483/201805/960483-20180508105815997-1505796350.jpg)

#### 知识点：use
vue的use源码：<br/>
![](https://images2018.cnblogs.com/blog/960483/201805/960483-20180508105459571-1871148443.jpg)<br/>
看源码我们可以知道在我们以后编写插件的时候可以有两种方式。
一种是将这个插件的逻辑封装成一个对象最后将最后在install编写业务代码暴露给Vue对象。这样做的好处是可以添加任意参数在这个对象上方便将install函数封装得更加精简，可拓展性也比较高。
还有一种则是将所有逻辑都编写成一个函数暴露给Vue。
其实两种方法原理都一样，无非第二种就是将这个插件直接当成install函数来处理。

#### button组件
button的功能不是很多，主要是样式，所以学习button组件大部分时间是看样式。vue组件在目录:<br/>
![](https://images2018.cnblogs.com/blog/960483/201805/960483-20180508115207800-1203586112.jpg)<br/>
组件样式目录：<br/>
![](https://images2018.cnblogs.com/blog/960483/201805/960483-20180508115434505-919002615.jpg)
<br/>
组件样式混入目录：<br/>
![](https://images2018.cnblogs.com/blog/960483/201805/960483-20180508115650661-615088118.jpg)

