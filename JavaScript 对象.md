# JavaScript Array 对象
1. 访问数组 
使用for in 遍历
关联数组  使用字符串作下标
2. 数组操作函数
toSting() 以逗号拼接而成
join()  指定分隔符拼接数组元素
concat () 拼接两个或以上数组 返回拼接后的副本 arr.concat (arr1,arr2) 
slice()获取指定数组中的子数组 arr.slice(start,[end]) 从开始到结束，不包含结束
splic()删除一部分元素，并添加另一部分元素 arr.splic(start,count,e1,e2)         start：指定添加或删除的起始位置 可负值，count要删除元素的个数 不删写0，e2,e2要添加的新元素
reverse() 倒转数组
sort()排序 默认升序unicode ,自定义函数排序
  fun sortAsc(a,b){return a-b}升序   fun sortAsc(a,b){return b-a}降序
  arr.sore(sortAsc) 使用函数排序 不加（） 会自己找sortAsc
  匿名函数 arr.sore(   fun sortAsc(a,b){return a-b} )
valueOf()	返回数组对象的原始值
3. 进出栈
push() 入栈，栈顶
pop()出栈，删除并返回栈顶元素
unshift()在数组头部添加新元素
shift（） 删除数组头部新元素并返回
4. Array 对象属性
 length	设置或返回数组中元素的数目。
 prototype	使您有能力向对象添加属性和方法。
 constructor	返回对创建此对象的数组函数的引用。


# JavaScript Math 对象
1. abs(x)	返回数的绝对值。
2. ceil(x)	对数进行上舍入。
3. floor(x)	对数进行下舍入。
4. exp(x)	返回 e 的指数。
5. max(x,y)	返回 x 和 y 中的最高值。
6. min(x,y) 返回 x 和 y 中的最低值。
7. random()	返回 0 ~ 1 之间的随机数。、
8. round(x)	把数四舍五入为最接近的整数。
9. valueOf()	返回 Math 对象的原始值。

#  JavaScript Date 对象
Date()	返回当日的日期和时间
getDate()	从 Date 对象返回一个月中的某一天 (1 ~ 31)。
getDay()	从 Date 对象返回一周中的某一天 (0 ~ 6)。
getMonth()	从 Date 对象返回月份 (0 ~ 11)。
getFullYear()	从 Date 对象以四位数字返回年份。
getYear()	请使用 getFullYear() 方法代替。
getHours()	返回 Date 对象的小时 (0 ~ 23)。
getMinutes()	返回 Date 对象的分钟 (0 ~ 59)。
getSeconds()	返回 Date 对象的秒数 (0 ~ 59)。
getMilliseconds()	返回 Date 对象的毫秒(0 ~ 999)。
getTime()	返回 1970 年 1 月 1 日至今的毫秒数。
parse()	返回1970年1月1日午夜到指定日期（字符串）的毫秒数。
UTC()	根据世界时返回 1970 年 1 月 1 日 到指定日期的毫秒数。
setDate()	设置 Date 对象中月的某一天 (1 ~ 31)。
toString()	把 Date 对象转换为字符串。
toTimeString()	把 Date 对象的时间部分转换为字符串。
toDateString()	把 Date 对象的日期部分转换为字符串。
valueOf()	返回 Date 对象的原始值。

#  JavaScript Number 对象
1. Number 对象属性
constructor	返回对创建此对象的 Number 函数的引用。
MAX_VALUE	可表示的最大的数。
MIN_VALUE	可表示的最小的数。
NaN	非数字值。
NEGATIVE_INFINITY	负无穷大，溢出时返回该值。
POSITIVE_INFINITY	正无穷大，溢出时返回该值。
prototype	使您有能力向对象添加属性和方法。
2. Number 对象方法
toString()	把数字转换为字符串，使用指定的基数。
toFixed(num)把数字转换为字符串，结果的小数点后有指定位数的数字。  num必须有0-20
valueOf()	返回一个 Number 对象的基本数字值。

# JavaScript String 对象
1. String 对象属性
length	字符串的长度
prototype	允许您向对象添加属性和方法
2. String 对象方法
replace(regexp/substr,replacement)	替换与正则表达式匹配的子串。
  egexp/substr 必需。规定子字符串或要替换的模式的 RegExp 对象。
  replacement 一个字符串值。规定了替换文本或生成替换文本的函数。
match(searchvalue/regexp) 
  searchvalue	必需。规定要检索的字符串值。
  regexp	必需。规定要匹配的模式的 RegExp 对象
big()	用大号字体显示字符串。
small()	使用小字号来显示字符串。
bold()	使用粗体显示字符串。
charAt(index)	返回在指定位置的字符。
charCodeAt(index)返回在指定的位置的字符的 Unicode 编码。
concat(stringX,stringX,...,stringX)	连接字符串。
fontcolor(color)	使用指定的颜色来显示字符串。
indexOf(searchvalue,fromindex)	检索字符串。
  searchvalue	必需。规定需检索的字符串值
  fromindex 规定在字符串中开始检索的位置，如省略该参数，则将从字符串的首字符开始检索。
  方法对大小写敏感！如果要检索的字符串值没有出现，则该方法返回 -1。
lastIndexOf(searchvalue,fromindex)	从后向前搜索字符串。
italics()	使用斜体显示字符串。
link()	将字符串显示为链接。
toLowerCase()	把字符串转换为小写。
toUpperCase()	把字符串转换为大写。
substring(start,stop)	提取字符串中两个指定的索引号之间的字符。
  start	必需。一个非负的整数
  stop	可选。一个非负的整数
substr(start,length)	从起始索引号提取字符串中指定数目的字符。
  start	必需。要抽取的子串的起始下标必须是数值。如果是负数，那么该参数声明从字符串的尾部开始算起的位置。也就是说，-1 指字符串中最后一个字符，-2 指倒数第二个字符
  length	可选。子串中的字符数。必须是数值。如果省略了该参数，那么返回从 stringObject 的开始位置到结尾的字串。
split(separator,howmany)	把字符串分割为字符串数组。
  separator	必需。字符串或正则表达式，从该参数指定的地方分割
  howmany	可选。该参数可指定返回的数组的最大长度

# JavaScript RegExp 对象
1. 修饰符
i	执行对大小写不敏感的匹配。
g	执行全局匹配（查找所有匹配而非在找到第一个匹配后停止）。直接量语法：/regexp/g
m	执行多行匹配。
2. 方括号
[abc]	查找方括号之间的任何字符。
[^abc]	查找任何不在方括号之间的字符。  /[^xyz]/
[0-9]	查找任何从 0 至 9 的数字。
(red|blue|green)	查找任何指定的选项。
3. 元字符 是拥有特殊含义的字符
.    元字符用于查找单个字符，除了换行和行结束符。 /regexp./ 对字符串中的 "h.t"       进行  全局搜索：/h.t/g; 
\w   元字符用于查找单词字符。 /\w/
\W	查找非单词字符。
\d	查找数字。
\D	查找非数字字符。
\s	查找空白字符。
\S	查找非空白字符。
\b	匹配单词边界。 对字符串中的单词的开头或结尾进行 "W3" 的全局搜索：/\bW3/g;
\B	匹配非单词边界。
\B	匹配非单词边界。
\0	查找 NUL 字符。
\n	查找换行符。
\f	查找换页符。
\r	查找回车符。
\t	查找制表符。
\v	查找垂直制表符。
\xxx 元字符用于查找以八进制数 xxx 规定的字符 对字符串中的八进制 127 (W) 进行全      局  搜索：=/\127/g
\xdd 元字符查找以十六进制数 dd 规定的字符。 对字符串中的十六进制 57 (W) 进行全      局  搜索：/\x57/g
4. 量词
n+	匹配任何包含至少一个 n 的字符串。
n*	匹配任何包含零个或多个 n 的字符串。
n?	匹配任何包含零个或一个 n 的字符串。
n{X}	匹配包含 X 个 n 的序列的字符串。
n{X,Y}	匹配包含 X 至 Y 个 n 的序列的字符串。
n{X,}	匹配包含至少 X 个 n 的序列的字符串。
n$	匹配任何结尾为 n 的字符串。
^n	匹配任何开头为 n 的字符串。
?=n	匹配任何其后紧接指定字符串 n 的字符串。
?!n	匹配任何其后没有紧接指定字符串 n 的字符串。
5. RegExp 对象属性
global	RegExp 对象是否具有标志 g。	 RegExpObject.global 返回true或false
ignoreCase	RegExp 对象是否具有标志 i。 返回true或false
multiline	RegExp 对象是否具有标志 m。 返回true或false
source	正则表达式的源文本。
lastIndex	一个整数，标示开始下一次匹配的字符位置。上一次匹配到的元素的下标加一
6. RegExp 对象方法
compile	编译正则表达式。
  RegExpObject.compile(regexp,modifier)
  regexp	正则表达式。
  modifier	规定匹配的类型。"g" 用于全局匹配，"i" 用于区分大小写，"gi" 用于全局区分大小写的匹配。
exec(string)	检索字符串中指定的值。返回找到的值，并确定其位置。 string	必需。  要检索的字符串。返回一个数组，其中存放匹配的结果。如果未找到匹配，则返回值为      null。
test(string) string	必需。要检测的字符串。则返回 true，否则返回 false。
7. 支持正则表达式的 String 对象的方法
search	检索与正则表达式相匹配的值。	
match	找到一个或多个正则表达式的匹配。	
replace	替换与正则表达式匹配的子串。	
split	把字符串分割为字符串数组。

# JavaScript 全局对象
isFinite()	检查某个值是否为有穷大的数。  number 是有限数字（或可转换为有限数     字），那么返回 true。
isNaN()	检查某个值是否是数字。
Number()	把对象的值转换为数字。
parseFloat()	解析一个字符串并返回一个浮点数。
parseInt(string, radix)	解析一个字符串并返回一个整数。 radix	
    可选。表示要解析的数字的基数。该值介于 2 ~ 36 之间。进制
String()	把对象的值转换为字符串。
escape()	对字符串进行编码。
unescape()	对由 escape() 编码的字符串进行解码
2. 顶层属性（全局属性）
Infinity	代表正的无穷大的数值。
NaN	指示某个值是不是数字值。isNaN() 来判断一个值是否是数字。NaN 与所有值都不相    等，包括它自己。
undefined  只能用 === 运算来测试某个值是否是未定义的

#  JavaScript 事件参考手册
onabort	图像加载被中断	1	3	4
onblur	元素失去焦点	1	2	3
onchange	用户改变域的内容	1	2	3
onclick	鼠标点击某个对象	1	2	3
ondblclick	鼠标双击某个对象	1	4	4
onerror	当加载文档或图像时发生某个错误	1	3	4
onfocus	元素获得焦点	1	2	3
onkeydown	某个键盘的键被按下	1	4	3
onkeypress	某个键盘的键被按下或按住	1	4	3
onkeyup	某个键盘的键被松开	1	4	3
onload	某个页面或图像被完成加载	1	2	3
onmousedown	某个鼠标按键被按下	1	4	4
onmousemove	鼠标被移动	1	6	3
onmouseout	鼠标从某元素移开	1	4	4
onmouseover	鼠标被移到某元素之上	1	2	3
onmouseup	某个鼠标按键被松开	1	4	4
onreset	重置按钮被点击	1	3	4
onresize	窗口或框架被调整尺寸	1	4	4
onselect	文本被选定	1	2	3
onsubmit	提交按钮被点击	1	2	3
onunload	用户退出页面	1	2	3