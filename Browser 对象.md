# Window 对象
frames[] 返回窗口中所有命名的框架。
2. Window 对象属性
closed	返回窗口是否已被关闭。
document	对 Document 对象的只读引用
history	对 History 对象的只读引用。
innerheight	返回窗口的文档显示区的高度。宽度和高度不包括菜单栏、工具栏以及滚动条  等的高度。
innerwidth	返回窗口的文档显示区的宽度。
outerheight	返回窗口的外部高度。
outerwidth	返回窗口的外部宽度。
length	设置或返回窗口中的框架数量。
defaultStatus	设置或返回窗口状态栏中的默认文本。
name	设置或返回窗口的名称。
location	用于窗口或框架的 Location 对象
Navigator	对 Navigator 对象的只读引用
pageXOffset	设置或返回当前页面相对于窗口显示区左上角的 X 位置。
pageYOffset	设置或返回当前页面相对于窗口显示区左上角的 Y 位置。
parent	返回父窗口。
Screen	对 Screen 对象的只读引用
self	返回对当前窗口的引用。等价于 Window 属性。
status	设置窗口状态栏的文本。
top	返回最顶层的先辈窗口。
window	window 属性等价于 self 属性，它包含了对窗口自身的引用。

# Window 对象方法
alert()	显示带有一段消息和一个确认按钮的警告框。
setInterval()	按照指定的周期（以毫秒计）来调用函数或计算表达式。
setTimeout()	在指定的毫秒数后调用函数或计算表达式。
clearInterval()	取消由 setInterval() 设置的 timeout。
clearTimeout()	取消由 setTimeout() 方法设置的 timeout。
scrollBy()	按照指定的像素值来滚动内容。
scrollTo()	把内容滚动到指定的坐标。
focus()	把键盘焦点给予一个窗口。
blur()	把键盘焦点从顶层窗口移开。
resizeBy()	按照指定的像素调整窗口的大小。
resizeTo()	把窗口的大小调整到指定的宽度和高度。
open()	打开一个新的浏览器窗口或查找一个已命名的窗口。
print()	打印当前窗口的内容。
prompt()	显示可提示用户输入的对话框。
resizeBy()	按照指定的像素调整窗口的大小。
moveBy()	可相对窗口的当前坐标把它移动指定的像素。
moveTo()	把窗口的左上角移动到一个指定的坐标。
confirm(message)	显示带有一段消息以及确认按钮和取消按钮的对话框。 纯文本
  如果用户点击确定按钮，则 confirm() 返回 true。如果点击取消按钮，则 confirm() 返回 false。
prompt(text,defaultText)	显示可提示用户输入的对话框。t
  ext	可选。要在对话框中显示的纯文本（而不是 HTML 格式的文本）。
  defaultText	可选。默认的输入文本。
  如果用户单击提示框的取消按钮，则返回 null。如果用户单击确认按钮，则返回输入字段当前显示的文本。
print()	打印当前窗口的内容。

# Navigator 对象  对象包含有关浏览器的信息。
1. Navigator 对象集合
返回对文档中所有嵌入式对象的引用。
该集合是一个 Plugin 对象的数组，其中的元素代表浏览器已经安装的插件。Plug-in 对象提供的是有关插件的信息，其中包括它所支持的 MIME 类型的列表。
2. Navigator 对象属性
cookieEnabled	返回指明浏览器中是否启用 cookie 的布尔值。
browserLanguage	返回当前浏览器的语言。
cpuClass	返回浏览器系统的 CPU 等级。
platform	返回运行浏览器的操作系统平台。
systemLanguage	返回 OS 使用的默认语言。
userLanguage	返回 OS 的自然语言设置。
userAgent	返回由客户机发送服务器的 user-agent 头部的值。
onLine	返回指明系统是否处于脱机模式的布尔值。
appCodeName	返回浏览器的代码名。
appMinorVersion	返回浏览器的次级版本。
appName	返回浏览器的名称。
appVersion	返回浏览器的平台和版本信息。
3. Navigator 对象方法
javaEnabled()	规定浏览器是否启用 Java。
taintEnabled()	规定浏览器是否启用数据污点 (data tainting)。

# Screen 对象
1. Screen 对象属性
availHeight	返回显示屏幕的高度 (除 Windows 任务栏之外)。
availWidth	返回显示屏幕的宽度 (除 Windows 任务栏之外)。
bufferDepth	设置或返回调色板的比特深度。
colorDepth	返回目标设备或缓冲器上的调色板的比特深度。
deviceXDPI	返回显示屏幕的每英寸水平点数。
deviceYDPI	返回显示屏幕的每英寸垂直点数。
fontSmoothingEnabled	返回用户是否在显示控制面板中启用了字体平滑。
height	返回显示屏幕的高度。
logicalXDPI	返回显示屏幕每英寸的水平方向的常规点数。
logicalYDPI	返回显示屏幕每英寸的垂直方向的常规点数。
pixelDepth	返回显示屏幕的颜色分辨率（比特每像素）。
updateInterval	设置或返回屏幕的刷新率。
width	返回显示器屏幕的宽度。
availHeight	返回显示屏幕的高度 (除 Windows 任务栏之外)。
availWidth	返回显示屏幕的宽度 (除 Windows 任务栏之外)。
bufferDepth	设置或返回调色板的比特深度。
colorDepth	返回目标设备或缓冲器上的调色板的比特深度。
deviceXDPI	返回显示屏幕的每英寸水平点数。
deviceYDPI	返回显示屏幕的每英寸垂直点数。
fontSmoothingEnabled	返回用户是否在显示控制面板中启用了字体平滑。
height	返回显示屏幕的高度。
logicalXDPI	返回显示屏幕每英寸的水平方向的常规点数。
logicalYDPI	返回显示屏幕每英寸的垂直方向的常规点数。
pixelDepth	返回显示屏幕的颜色分辨率（比特每像素）。
updateInterval	设置或返回屏幕的刷新率。
width	返回显示器屏幕的宽度。
# History 对象
对象包含用户（在浏览器窗口中）访问过的 URL。
1. History 对象属性
length	返回浏览器历史列表中的 URL 数量。
2. History 对象方法
back()	加载 history 列表中的前一个 URL。
forward()	加载 history 列表中的下一个 URL。
go()	加载 history 列表中的某个具体页面。

# Location 对象
1. Location 对象包含有关当前 URL 的信息。
2. Location 对象属性
hash	设置或返回从井号 (#) 开始的 URL（锚）。
host	设置或返回主机名和当前 URL 的端口号。
hostname	设置或返回当前 URL 的主机名。
href	设置或返回完整的 URL。
pathname	设置或返回当前 URL 的路径部分。
port	设置或返回当前 URL 的端口号。
protocol	设置或返回当前 URL 的协议。
search	设置或返回从问号 (?) 开始的 URL（查询部分）。
2. Location 对象方法
assign()	加载新的文档。
reload()	重新加载当前文档。
replace()	用新的文档替换当前文档。
