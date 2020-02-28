# 变量提升 function提升
var 声明的变量会提升，值还在原来的位置
function声明的函数会整体提升
提升的var 变量名和function名冲突，会优先保留fun

# 优先级
fo().getname()
.的优先级最高，如果fo()还没有。属性才会先执行fo()

new fun( ) 会优先处理函数调用，再创建实例对象
new fun( )。getname() .的优先级最高，但是如果fun()没有.属性会变成(new foo( ))。getname()   延原型链找，先去foo构造函数找getname 如果没有回去构造函数原型上找

# 变量的查找规则，延作用域链查找
function 中的变量没有使用var定义，会提升到全局作用域将全局作用域的变量值替换掉
function foo(){
  return this;
}
foo调用其实是window。foo调用，this指向window 即 foo().getname是window.getname

# 什么是函数节流和函数防抖
10. 函数节流：一个函数执行一次后，只有大于设定的执行周期才会执行第二次
需要频繁触发函数，处于优化性能角度，在规定时间内，只让函数触发第一次生效

  节流函数
  @fn 要被节流的函数
  delay 规定的时间
  function throttle(fn,delay){
    //记录上一次触发的时间
    var lastTime=0;
    return function(){//利用闭包方式，执行函数调用防止多次初始化为0
      //记录当前函数触发时间
    var nowTime=Date.now();
    if(nowTime-lastTime>delay){
      <!-- fn(); -->
      fn.call(this)//修正this指向问题
      lastTime=nowTime
    }
    }
  }
2. 防抖函数
一个需要频繁出发的函数，在规定时间内，只让最后一次生效，前面不生效
function throttle(fn,delay){
  //记录上一次延时器
  var time=null;
  return function(){
    //清除上一次延时器
    clearTimeout(time);
    //重新设置延时器
    time=setTimeout(function(){
      fn.apply(this); //修正this指向问题
    },delay)
  }
}
#   apply:方法能劫持另外一个对象的方法，继承另外一个对象的属性.
  call:和apply的意思一样,只不过是参数列表不一样.
  Function.apply(obj,args)方法能接收两个参数
obj：这个对象将代替Function类里this对象
args：这个是数组，它将作为参数传给Function（args-->arguments）

         call:和apply的意思一样,只不过是参数列表不一样.

 Function.call(obj,[param1[,param2[,…[,paramN]]]])
obj：这个对象将代替Function类里this对象
params：这个是一个参数列表

# 什么是跨域，有哪些方法
1. 同源策略
  浏览器安全策略
  协议名，域名，端口号必须一致
  2. 跨域 
  多台服务器协同工作，违背同源策略
  3. 解决跨域
  jsonp cors 服务器代码
  jsonp利用script标签天然跨域

  # nodejs事件轮询机制
  //顺序如下，跟函数位置无关
  process.nextTick() //任意阶段优先执行
  setTimeout()
  setImmediate()

  1. 借助libuv库实现的
  vu_run
  分为六个阶段
  1. timers定时器阶段
  定时和执行到点的定时器回调函数
  2. pending callbacks
  某些系统操作例如tcp错误的回调函数
  3. idle prepare
  准备工作
  4. poll 轮训阶段（轮训队列）
    如果轮训队列不为空，依次取出队列的第一个函数，直到轮训队列为空或系统最大限制
    如果为空
      如果之前设置过setImmediate函数
      直接进入下一个check阶段
      如果之前没有设置过setImmediate函数
        在当前poll阶段等待
        直到轮训队列添加回调函数，就去执行第一个情况执行
        如果定时器到点，也会去执行下一阶段
  5. check阶段
      setImmediate设置的回调函数
  6. close callback关闭阶段，
      close事件回调函数
# 从url地址到最终页面渲染完成
1. dns解析，将域名地址解析为IP地址
    -浏览器dns缓存
    系统dns缓存
    路由器dns缓存
    网络运营商dns缓存
    递归搜索：blog.baidu.com
      com域名下查找DNS解析
      baidu下查找DNS解析
      blog下查找DNS解析
      出错了
 2.  tcp连接 tcp三次握手
  1 浏览器发起，告诉服务器我要发起请求
  2 服务器发起，告诉浏览器我准备接收了
  3 浏览器发送 告诉服务器，我马上就发了
3. 发送请求 
  请求报文 ：http协议的通信内容
4. 接收响应
  响应报文
5. 渲染页面
  遇见html标记，浏览器调用HTML解析器解析成TOKEN并构成dom树
  遇见style、link标记，浏览器会调用css解析器，处理css标记cssom树
  遇见script标记，浏览器会调用javascript解析器，处理javascript绑定事件修改dom树cssom树
  将树合并，成一个渲染树
  根据渲染树计算布局，计算每个节点几何信息（布局）
  将各个节点颜色绘制到屏幕上（渲染）

  注意 
    这五个步骤不一定按顺序执行，如果dom树cssom树被修改，可能会执行多次
6. 断开连接 tcp四次挥手
    1  浏览器发起，告诉服务器我要发报文发完
    2 浏览器发起，告诉服务器接收完了
    3 服务器发起，告诉浏览器我东西发完，你准备关闭
    4 浏览器发起，告诉服务器我东西接收完，你准备关闭吧






# 闭包
  1. 密闭的容器，类似于set ，map容器，存储数据的
  2. 闭包是一个对象 ，存放格式键值对 key=>value
  形成条件
  1. 函数嵌套
  2. 内部函数引用外部函数的局部变量
  闭包的优点
  延长外部局部变量的生命周期
  闭包的缺点
  容易造成内存泄漏
  注意点：
  合理使用闭包
  用完及时销毁，避免内存泄漏
# 变量提升 预处理
js 引擎在代码正式执行前会做一个预处理工作
1. 收集变量
2. 收集函数
var只收集变量不赋值
fun提前定义好 
console。log(a)//undefind 因为变量名提升了，只是值未定义
var a=1

* 执行上下文（execute context)EC
理解：代码执行的环境
时机：代码正式执行之前会进入执行环境
工作：
  创建变量对象
    变量
    函数及函数参数
    全局：window
    局部：抽象但确实存在
  确定this的指向
    全局 this=》Windows
    局部this=》调用其对象
  创建作用域链
    父级作用域+当前的变量对象
  扩展：
    ECobj={
      变量对象：{变量，函数，函数的形参}
      acopeChain:父级作用域+当前的变量对象
      this:{》Windows,调用其对象}
    }
# 宏任务和微任务
宏任务
  分类：setTimeout setInterval requrestAnimationFram
  1.被放置在宏任务队列的任务
  2.第一个宏任务队列只有一个任务：执行主线程JS代码
  3.宏任务队列可以有多个
  4.当一个宏任务队列中的任务全部执行完以后会查看微任务队列是否有任务如果有，会执行完微任务队列的任务，如果没有，查看是否有宏任务队列
微任务
  分类 ：new Promise().then(回调)process.nextTick
   1.被放置在微任务队列的任务
   2.只有一个微任务队列
   3.在上一个宏任务队列执行完毕后如果有微任务就会执行微任务中的所有任务
new Promise是同步任务 
# react和vue的比较
mv*
都组件化开发和virtualDOM（虚拟OM
都支持PROPS父子组件间数据通信
支持数据驱动视图
都支持服务器渲染
都支持native 的方案，react的reactNative vue的vuex
2. 不同点
* 支持双向数据绑定：vue react数据是单向的，内存到界面的变化
* 组件写法不一样，react推荐的jsx,就是把html和js写在js里面即“all in js;vue推荐做法：webpack+vue+loader的单文件组件形式，HTML css js写在同一个文件
* state在react中是不可变得，需要setState方法更新状态，在vue中state不是必须的，数据有data属性在vue对象中管理
* virtualDOM 不一样vue会跟中每一个组件的依赖关系，不需要从新渲染整个组件树，而对react而言，每当应用的状态发生改变时，全部组件都要重新渲染，所以react中需要用shouldComponentUndata这个生命周期来控制
* react严格来说是只针对MVC的view，vue则是mvvm模式
vue官方化 react社区化
* react修改配置需要下载第三方库
* react中高阶组件使用较多
# redux状态管理机制
redux是一个专门用于状态管理的js库，而不是react插件
可以在react vue angular 项目，但基本与react搭配使用
集中式管理react应用的多个组件共享的状态，和从后台获取的数据
3. redux使用扩展
使用react-redux简化redux的编码
使用redux-thunk实现redux异步编程
使用redux DevTools 实现Chrome中redux的调试
# vue组件间通信方式
1. 通信的种类
父向子通信
子向父通信
隔代通信
兄弟通信
2. 通信的实现
props
vue自定义事件
消息订阅与发布
vuex
slot
3. props 
标签方式 
通过一般属性实现父向子通信
通过函数实现子向父通信
缺点：隔代，兄弟通信比较麻烦
4. vue自定义事件
vue内置实现可代替函数类型的props
   绑定监听《myComp @eventName="callback"
   触发分发事件：this.$emit("eventName",data)
  缺点，只适合子向父通信
5. 消息的订阅与发布
  需要引入消息的订阅与发布的实现库 如pubsub-js
  a 订阅消息 如pubsub.subscribe("msg",function(msg,daata){})
  b 发布消息：如pubsub。publish(msg,daata)
  优点：实现任意组件方式
6. vuex 
官方提供的集中管理的vue插件
没有组件限制
7. slot
专门用来实现父向子传递带数据的标签
  子组件
  父组件
  通信标签莫板是在父组件中解析好后再传递给子组件的
# vuex
1. vuex理解
是一个专门为vue.js应用程序开发的状态管理vue插件
作用：集中式管理vue多个组件共享状态 和从后台获取数据
# vue的mvvm实现原理
1. vue作为mvvm的模式实现的两种技术
模板解析
数据绑定
2. 模板解析：实现初始化显示
解析大括号表达式
指令解析
3. 数据绑定
 通过数据劫持实现
 4. 原理
