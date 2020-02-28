### 兼容性查询网站 can i use
# background
background:rgba(255,255,255,.3) 半透明
background :url(img.jpg) no-repeat //不平铺 背景不重复
# 优先级权重
1. 就近原则 权重叠加，不进位
标签 0001
类 伪类 0010
id 0100
行内 1000
！important  最大
* 或 继承0000 

# position
relative 比标准流高一点
fixed 固定定位,只认浏览器 top lift 必须有  IE6不兼容 模拟absolute 禁掉html的滚动：html:{overfolw:hidden,height:100%} 让body自动 body:{overflow:auto,}
absolute
static 默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right 或者 z-index 声明）
inherit	规定应该从父元素继承 position 属性的值。
1. 元素添加绝对定位和固定定位，会转化为为行内块模式，行内元素若添加了，可以不用转换模式，直接给高度和宽度就可以了 高宽跟内容有关没给宽度时
# dispaly
 父级 display:flex;
flex-direction: row | row-reverse | column | column-reverse;
flex:auto
flex-wrap: nowrap | wrap | wrap-reverse;

# Z-index -1 拥有更低的优先级 比0
数字越大越优先， 后来者优先


overflow:hidden 溢出隐藏
overflow:scroll 滚动  body或HTML都有，body上的才作用于body，只有        一个有只做用于文档（html的容器
overflow:auto 超出滚动
文本溢出变省略号{
  disply:bolck
  text-overflow：ellipsis ；
  white-space：nowrap;
  overflow:hidden;
}
cursor：pointer 让鼠标样式变小手
cursor：text 让鼠标样式变选择样式
cursor：move 让鼠标样式变十字架
cursor：default 让鼠标样式变箭头

outline：none 取消轮廓线

textarea {resize:none} 防止拖拽

vartical-align 垂直对齐  行内块 行内元素搭配使用，不影响块元素
baseline 基线对齐，图片文字默认
middle 垂直居中
top 顶部对齐

# footer 黏连布局 当内容较短，出现在屏幕底部
<body><div warp><div id='main'></div><div id='foot'></div></body>

# bfc 块级格式化上下文
1. 内部规则
块级独占一行
不与float box重叠
内部的box垂直方向的距离由margin决定,属于同一个bfc的两个相邻的box，margin会重叠
计算bfc的高度时，浮动元素也参与计算（清除浮动haslayout)
bfc就是页面上一个隔离的独立容器，容器内外的元素不会互相影响
2. 那些元素生成
根元素
float 属性不为none
postion为absolute或fixed
overflow不为visible
display为inline-block table-cell,table-caption,FLEX.,inline-flex

# 清除浮动
1. 给父级元素加高度（扩展性不好
2. 开启bfc 对于父级元素（ie6 7 不支持
  overflow：hidden
  定位
  浮动
3. br标签
  ie6不支持
4. 空标签
  违反结构行为 样式分离原则
    ie6下元素最小高度1px
      可以尝试给元素的fontsize设置为0实际变为2px
5. 伪元素+开启haslayout
  ie6不支持伪元素
  需要额外开启haslayout
  .a{
    *zoom:1//缩放比，开启haslayout
  }
  .a:after{
    content:'',
    display:block;
    clear:both;
  }
# hack 可减少开销性能 可以检测IE版本
  针对IE6 7 高版本不认 * 
    用在属性上 

# postcss 处理兼容问题

# flex 不等同于浮动（作用于自己），作用于父元素，当子元素总大小大于父元素宽度时，flex新版本会自动缩小，-webkit-box老版本会显示一行，超出父元素宽度溢出
flex容器（父
flex项目（子
主轴 x轴
侧轴 y轴
项目永远排列在主轴
-webkit-box-orient:vertical//老，以Y为主轴，布局方向
flex-direction:column      //新，以Y为主轴 布局方向
-webkit-box-direction ：reverse      //老，决定主轴方向，从头倒排
flex-direction:column-reverse      //新，以Y为主轴决定主轴方向，从末尾倒排
富余空间
1. 老版 主轴
-webkit-box-pack:start
start 富裕空间在右边（x)/下（y)
end 富裕空间在左边（x)/上（y)
center 在两边
justify 在项目之间
2. 新版 主轴
justify-content：flex-start
flex-start 主轴正方向
flex-end   主轴反方向
center 在两边
space-between 在项目之间
space-around 在项目两间
3. 老版 侧轴
-webkit-box-align:start
start 富裕空间在下（x)/右边（y)
end 富裕空间在上（x)/左边（y)
center 在两边
4. 新版 侧轴
align-items:flex-start 单列起作用
flex-start 侧轴正方向
flex-end   侧轴反方向
center 在侧轴两边
baseline 按基线对齐
stretch  等高布局
5. 新增
flex-wrap:wrap-reverse 多余换行，倒排主轴正方向（控制侧轴方向）
flex-wrap:wrap 多余换行，主轴正方向
align-content：flex-start （多列起作用，所有行列看做一个整体
flex-flow 控制主轴侧轴方向 flex-wrap和flex-direction简写
6. 作用于项目（非父）
order ：5 数值越大越在后
align-self ：flex-end 以自己的侧方向排，不安父容器
flex-grow：1 默认值为0 定义拉伸因子，可用空间=容器大小-所有相邻项目flex-basis的总和，每项伸缩大小=伸缩基准值+（可用空间/所有相邻项目flex-grow的总和）*flex-grow值 ；基准值是本身值
box—flex：1 默认值为0
flex-shrink 在flex-wrap :nowrap时成立，默认值为1 收缩；移除空间按flex-shrink计算。为1时，减去项目收缩因数*负溢出空间。收缩因数=基数/总长度；
且不能小于内容宽度；递归收缩，一个空间不够，别的继续拉缩，给它留够空间
# 多列布局
width：600px;
column-width:100px;//分五列
column-width:5;//分五列
column-gap:40px; 间距
column-rule:solid ; 分割线


# 掌握 box-sizing 圆角 背景
# transition （过渡周期 过渡样式 过渡样式 过渡延迟，）多个过渡中间用逗号隔开  同一个元素，使用它要一致
1. css，js解析速度快，异步，比画布局快，会先按css样式过渡，待布局画好后会按新的过渡样式过渡
2. transition 在元素首次渲染还没有结束的情况下不会触发，首次渲染结束前改变样式不会出现过渡（初始化就改了）
3. 只让transfrom 过渡，不让transfrom-origin过渡：transition：3s transfrom
# transfrom 2d
translateX/Y 向x或y平移
translate ：10px 10px 45度平移
rotate 旋转 90edg
skew   斜切 45deg  斜拉扁长
transfrom ：scale（2）  缩放 2  放大xy各两倍
transfrom-origin：改变旋转基准点
# transfrom 3d
1. perspective 景深 物体距离眼睛的距离，肉眼距离屏幕的水平距离，让3D场景有近大远小的效果 写在父元素，作用于后代元素 perspective：200px
transfrom：perspective(200px) 作用于本身，perspective 必须放在首位（一般不这这样用，用第一种写在父元素上的方法）
原理：景深越大，灭点越远，元素变形更小
景深基点视角位置：perspective-origin：50% 50%（默认值）
景深叠加：父子景深会叠加，作用于孙元素。每款浏览器计算规则都不一样，尽量避免
2. transfrom:rotate3d(x,y,z,90edg)  放在translateZ后面不影响translateZ效果
3. translateZ大于于等于景深，导致景象贴脸上或看不到，且不能写百分比。配合景深有3d效果
4. transfrom:scaleZ(2) translateZ(100px) 单独使用没意义，组合使用等同于translateZ(200px)
5. transform-style：preserve-3d 营造一个有层级的3D舞台，是一个不可继承的属性，作用于子元素。有3D舞台效果，元素可以旋转到背景后面
6. backface-visibility ：hidden/visible 是否显示背面  



# animation动画
{animation-name:move//应用动画的名字
  nimation-duration：3s//动画运行时间
  animation-time-function:linear
  animation-time-function（执行快慢）ease-in 从慢到快）ease-out块->慢 linear匀速 steps(2,start/end)每个关键帧之间走两次 start看不见第一帧 end看不见最后一帧
  animation-delay:2s//延迟3秒后开始，动画外属性
  animation-interation-count:3//执行几次，动画内属性，重复的是关键帧
  animation-direction:reverse//执行的方向反转的是关键帧(从to到from)和
   animation-direction：alternate//s型执行 
  animation-fill-mode：backwards/forwards/both //控制元素在动画外的状态 backwards from之前的状态和from状态保持一致；forwards to之后与to保持一致
  backwards-play-state：paused/running 控制动画暂停
}
简写 animation：move 3s 2s 
@keyframes move{
  from(或0%）{
    transform:rotate(0deg)
  }
  to{
    transform:rotate(360deg)
  }
}
1. 关键帧 eg: from (0%)  to (100%) 代表动画运行总时间的百分之多少，也可替换成百分比。通过时间和路程来控制速度，animation-time-function用来控制两个关键帧之间的快慢
# 元素Width的获取
offsetWidth       //返回元素的宽度（包括元素宽度、内边距和边框，不包括外边距）

offsetHeight      //返回元素的高度（包括元素高度、内边距和边框，不包括外边距）

clientWidth        //返回元素的宽度（包括元素宽度、内边距，不包括边框和外边距）

clientHeight       //返回元素的高度（包括元素高度、内边距，不包括边框和外边距）

style.width         //返回元素的宽度（包括元素宽度，不包括内边距、边框和外边距）

style.height       //返回元素的高度（包括元素高度，不包括内边距、边框和外边距）

scrollWidth       //返回元素的宽度（包括元素宽度、内边距和溢出尺寸，不包括边框和外边距），无溢出的情况，与clientWidth相同

scrollHeigh       //返回元素的高度（包括元素高度、内边距和溢出尺寸，不包括边框和外边距），无溢出的情况，与clientHeight相同

1. style.width 返回的是字符串，如28px，offsetWidth返回的是数值28；

2. style.width/style.height与scrollWidth/scrollHeight是可读写的属性，clientWidth/clientHeight与offsetWidth/offsetHeight是只读属性

3. style.width的值需要事先定义，否则取到的值为空。而且必须要定义在html里(内联样式)，如果定义在css里，style.height的值仍然为空，但元素偏移有效；而offsetWidth则仍能取到。
-----------------------------------------
offsetTop    //返回元素的上外缘距离最近采用定位父元素内壁的距离，如果父元素中没有采用定位的，则是获取上外边缘距离文档内壁的距离。

所谓的定位就是position属性值为relative、absolute或者fixed。回值是一个整数，单位是像素。此属性是只读的。

offsetLeft       //此属性和offsetTop的原理是一样的，只不过方位不同，这里就不多介绍了。

scrollLeft        //此属性可以获取或者设置对象的最左边到对象在当前窗口显示的范围内的左边的距离，也就是元素被滚动条向左拉动的距离。

 返回值是一个整数，单位是像素。此属性是可读写的。

scrollTop   //此属性可以获取或者设置对象的最顶部到对象在当前窗口显示的范围内的顶边的距离，也就是元素滚动条被向下拉动的距离。

返回值是一个整数，单位是像素。此属性是可读写的。
---------------------------------------------------
当鼠标事件发生时（不管是onclick，还是omousemove，onmouseover等）

clientX        鼠标相对于浏览器（这里说的是浏览器的有效区域）左上角x轴的坐标；  不随滚动条滚动而改变；

clientY        鼠标相对于浏览器（这里说的是浏览器的有效区域）左上角y轴的坐标；  不随滚动条滚动而改变；

pageX        鼠标相对于浏览器（这里说的是浏览器的有效区域）左上角x轴的坐标；  随滚动条滚动而改变；

pageY        鼠标相对于浏览器（这里说的是浏览器的有效区域）左上角y轴的坐标；  随滚动条滚动而改变；

screenX     鼠标相对于显示器屏幕左上角x轴的坐标；  

screenY      鼠标相对于显示器屏幕左上角y轴的坐标；  

offsetX        鼠标相对于事件源左上角X轴的坐标

offsetY        鼠标相对于事件源左上角Y轴的坐标
# li:nth-child() 选子元素
# div内容平铺，white-space ：nowrap
# 调试 debugger
# 按下esc =》ntework con可以调网速
# 规范
1. js规范制定者 ecma和w3c
http://www.ecma-international.org/
ECMA404  JSON规范
ECMA262   js基础规范
欧洲计算机厂家协会;
这个组织的目标是评估，开发和认可电信和计算机标准
2. DOM规范制定者W3C(万维网联盟)
https://www.w3.org/
https://www.w3.org/DOM/Activity
DOM是规范，能被多个语言引用
先有DOM后有规范，所以没有DOM0

dom接口定义语言：IDL
HTML需要浏览器渲染xml不需要。他是特殊的xml
htmlDocument=>核心规范里面的document=>node
element=>node
规范向后兼容：把子规范里面的接口方法向上提
MDN=>网络 技术=>web api





w3c a to z 
学习教材：mdn 菜鸟教程 w3cschool
# BOM规范浏览器规范还没有，参照MDN中的window
# CSS规范
https://www.w3.org/Style/CSS/current-work
ed编辑草案
wd工作草案
lcwd最后通告工作草案（过渡阶段）
cr候选推荐标准
pr建议推荐标准
# HTML5 
它是一个新版本的HTML语言，具有新的元素，属性和行为，
它有更大的技术集，允许构建更多样化和更强大的网站和应用程序。这个集合有时称为HTML5和它的朋友们，不过大多数时候仅缩写为一个词 HTML5。
css+js+html 技术集


# 文字最下边是以基线对齐，
vertical-align: middle

# 缩进
text-indent:



# 不换行
white-space: nowrap;
overflow: hidden;
text-overflow: ellipsis;
超出部分省略号显示，不换行
# 字体间距
letter-spacing


# 用css写出三角形
box{
  width:0px;
  height:0px;
  border:100px solid;
  border-top-color:red;
  border-right-color:transparent;
  border-lift-color:transparent;//透明色
  border-bottom-color:transparent;
}
# 移动端rem适配
//html根元素字体大小设置屏幕区域的宽 1rem
window.onload=function(){
  //获取屏幕区域的宽度
  var width=document.documentElement.clientWidth;
  //获取html
  var htmlNode=document.querySelector('html');
  //设置字体大小
  htmlNode.style.fontSize=width+'px';
}

# 背景图片左边到box盒子左边框外侧的距离
bg-img默认在paddingbox的左上角
即paddingBox-borderBox的距离border的宽
bg-origin:content-box //修改背景图片默认位置为contentBox

