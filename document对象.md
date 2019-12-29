# Document 对象 
每个载入浏览器的 HTML 文档都会成为 Document 对象。

1. Document 对象集合 
all[]	提供对文档中所有 HTML 元素的访问。
anchors[]	返回对文档中所有 Anchor 对象的引用。
applets	返回对文档中所有 Applet 对象的引用。
forms[]	返回对文档中所有 Form 对象引用。
images[]	返回对文档中所有 Image 对象引用。
links[]	返回对文档中所有 Area 和 Link 对象引用。
2. Document 对象属性
body 供对 <body> 元素的直接访问。对于定义了框架集的文档，该属性引用最外层的       <frameset>。
cookie	设置或返回与当前文档有关的所有 cookie。
domain	返回当前文档的域名。
lastModified	返回文档被最后修改的日期和时间。
referrer	返回载入当前文档的文档的 URL。
title	返回当前文档的标题。
URL	返回当前文档的 URL。
3. Document 对象方法
close()	关闭用 document.open() 方法打开的输出流，并显示选定的数据。
getElementById()	返回对拥有指定 id 的第一个对象的引用。
getElementsByName()	返回带有指定名称的对象集合。
getElementsByTagName()	返回带有指定标签名的对象集合。
open()	打开一个流，以收集来自任何 document.write() 或 document.writeln() 方法的输出。
write()	向文档写 HTML 表达式 或 JavaScript 代码。
writeln()	等同于 write() 方法，不同的是在每个表达式之后写一个换行符。

# HTML DOM Element 对象
 HTML DOM 节点
 1. 属性和方法
element.appendChild()	向元素添加新的子节点，作为最后一个子节点
element.className	设置或返回元素的 class 属性。
element.clientHeight	返回元素的可见高度。
element.clientWidth	返回元素的可见宽度。
element.dir	设置或返回元素的内容是否可编辑。
element.firstChild	返回元素的首个子。
element.lastChild	返回元素的最后一个子元素。
element.getAttribute()	返回元素节点的指定属性值。
element.getElementsByTagName()	返回拥有指定标签名的所有子元素的集合。
element.hasAttribute()	如果元素拥有指定属性，则返回true，否则返回 false。
element.hasAttributes()	如果元素拥有属性，则返回 true，否则返回 false。
element.hasChildNodes()	如果元素拥有子节点，则返回 true，否则 false。
element.id	设置或返回元素的 id。
element.innerHTML	设置或返回元素的内容。
element.insertBefore()	在指定的已有的子节点之前插入新节点。
  ocument.getElementById("myList").insertBefore(newItem,existingItem);
element.isEqualNode()	检查两个元素是否相等。
element.isSameNode()	检查两个元素是否是相同的节点。element.lang	设置或返回元素的语言代码。
element.nodeName	返回元素的名称。
element.nodeType	返回元素的节点类型。
element.nodeValue	设置或返回元素值。
element.offsetHeight	返回元素的高度。
element.offsetWidth	返回元素的宽度。
element.offsetLeft	返回元素的水平偏移位置。
element.offsetParent	返回元素的偏移容器。
element.offsetTop	返回元素的垂直偏移位置。
element.ownerDocument	返回元素的根元素（文档对象）。
element.parentNode	返回元素的父节点。
removeAttribute("style")从元素中移除指定属性。
element.removeAttributeNode()	移除指定的属性节点，并返回被移除的节点。
element.removeChild()	从元素中移除子节点。
element.replaceChild()	替换元素中的子节点。
element.scrollHeight	返回元素的整体高度。
element.scrollWidth	返回元素的整体宽度。
element.scrollLeft	返回元素左边缘与视图之间的距离。
element.scrollTop	返回元素上边缘与视图之间的距离。
element.setAttribute()	把指定属性设置或更改为指定值。
element.setAttributeNode()	设置或更改指定属性节点。
element.setIdAttribute()	
element.setIdAttributeNode()	
element.setUserData()	把对象关联到元素上的键。
element.style	设置或返回元素的 style 属性。
element.tagName	返回元素的标签名。
element.textContent	设置或返回节点及其后代的文本内容。
element.title	设置或返回元素的 title 属性。
element.toString()	把元素转换为字符串。
nodelist.item()	返回 NodeList 中位于指定下标的节点。
nodelist.length	返回 NodeList 中的节点数。

# HTML DOM Attribute 对象
attr.isId	如果属性是 id 类型，则返回 true，否则返回 false。
attr.name	返回属性的名称。
attr.value	设置或返回属性的值。
nodemap.getNamedItem()	从 NamedNodeMap 返回指定的属性节点。
nodemap.item()	返回 NamedNodeMap 中位于指定下标的节点。
nodemap.length	返回 NamedNodeMap 中的节点数。
nodemap.removeNamedItem()	移除指定的属性节点。
nodemap.setNamedItem()	设置指定的属性节点（通过名称）。
# HTML DOM Event 对象
1. 事件句柄
onabort	图像的加载被中断。
onblur	元素失去焦点。
onchange	域的内容被改变。
onclick	当用户点击某个对象时调用的事件句柄。
ondblclick	当用户双击某个对象时调用的事件句柄。
onerror	在加载文档或图像时发生错误。
onfocus	元素获得焦点。
onkeydown	某个键盘按键被按下。
onkeypress	某个键盘按键被按下并松开。
onkeyup	某个键盘按键被松开。
onload	一张页面或一幅图像完成加载。
onmousedown	鼠标按钮被按下。
onmousemove	鼠标被移动。
onmouseout	鼠标从某元素移开。
onmouseover	鼠标移到某元素之上。
onmouseup	鼠标按键被松开。
onreset	重置按钮被点击。
onresize	窗口或框架被重新调整大小。
onselect	文本被选中。
onsubmit	确认按钮被点击。
onunload	用户退出页面。
2. 鼠标 / 键盘属性
altKey	返回当事件被触发时，"ALT" 是否被按下。 event.altKey=true|false|1|0
button	返回当事件被触发时，哪个鼠标按钮被点击。
clientX	返回当事件被触发时，鼠标指针的水平坐标。
clientY	返回当事件被触发时，鼠标指针的垂直坐标。
ctrlKey	返回当事件被触发时，"CTRL" 键是否被按下。
metaKey	返回当事件被触发时，"meta" 键是否被按下。
relatedTarget	返回与事件的目标节点相关的节点。
screenX	返回当某个事件被触发时，鼠标指针的水平坐标。
screenY	返回当某个事件被触发时，鼠标指针的垂直坐标。
shiftKey	返回当事件被触发时，"SHIFT" 键是否被按下。
3. IE 属性
cancelBubble	如果事件句柄想阻止事件传播到包容对象，必须把该属性设为 true。
fromElement	对于 mouseover 和 mouseout 事件，fromElement 引用移出鼠标的元素。
keyCode	对于 keypress 事件，该属性声明了被敲击的键生成的 Unicode 字符码。对于 keydown 和 keyup 事件，它指定了被敲击的键的虚拟键盘码。虚拟键盘码可能和使用的键盘的布局相关。
offsetX,offsetY	发生事件的地点在事件源元素的坐标系统中的 x 坐标和 y 坐标。
returnValue	如果设置了该属性，它的值比事件句柄的返回值优先级高。把这个属性设置为 fasle，可以取消发生事件的源元素的默认动作。
srcElement	对于生成事件的 Window 对象、Document 对象或 Element 对象的引用。
toElement	对于 mouseover 和 mouseout 事件，该属性引用移入鼠标的元素。
x,y	事件发生的位置的 x 坐标和 y 坐标，它们相对于用CSS动态定位的最内层包容元素。
4. 标准 Event 属性
bubbles	返回布尔值，指示事件是否是起泡事件类型。
cancelable	返回布尔值，指示事件是否可拥可取消的默认动作。
currentTarget	返回其事件监听器触发该事件的元素。
eventPhase	返回事件传播的当前阶段。
target	返回触发此事件的元素（事件的目标节点）。
timeStamp	返回事件生成的日期和时间。
type	返回当前 Event 对象表示的事件的名称。
5. 标准 Event 方法
initEvent()	初始化新创建的 Event 对象的属性。
preventDefault()	通知浏览器不要执行与事件关联的默认动作。
stopPropagation()	不再派发事件。