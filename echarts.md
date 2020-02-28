# 数据可视化定义
  借助图形化手段，清晰有效的传达与沟通信息
  科学可视化，信息可视化，可视化分析
  1. 科学可视化
    医疗科研航天领域
  2. 信息可视化
    信息堆积，提取出来，经过二次加工展现出来
  3. 数据分析
    数据接入 数据集合 数据处理 可视化 数据展示
  4. 价值
    降低决策风险 预测未来。总结过去
  5. 数据可视化软件：sas spss studio
  6. 数据可视化的书： 数据可视之美 鲜活的数据 可视化沟通 图解力 最简单的图形与最复杂的信息
  7. 动态切换 值域漫游 数据区域缩放 多图联动 百搭时间轴 大规模散点 力导向布局 动态数据的添加 多维度图里开关 商业BI 混搭 高度个性能力 特效 
# 网址https://www.echartsjs.com/zh/option.html#title
# echrts 放在dom的后面加载，防止dom元素没有加载完就开始操作dom
# 零编程写echarts：百度图说
https://tushuo.baidu.com/wave/index#/manufacture/dta98yzwfy6dkcowc/999
# 个性化地图
http://lbsyun.baidu.com/index.php?title=jspopular3.0/guide/custom
# 常用图表
  1. line 折线/面积图
    * polyline ：true 是否为多段线，用于绘制轨迹，默认false
    * markPoint 图表标注
    * markLine 图表标线 
  2. bar 柱状/条形图
    barwidth:1 柱子宽度是1
  3. pie 饼图
    * radius :['30%','50%'], 半径的长55%的环内环30%
    * label：每个item的标签
      1. normal
        * position：outside 标签的位置
        * show：false 是否显示所有标签
      2. emphasis
        * show ：true 是否显示被选中的标签
        * formatter……被选中便签的格式样式
    * series可以是一个数组，这样可以嵌套多个环
  4. scatter 散点（气泡）图
    * symbol 标记的图形。 'circle', 'rect', 'roundRect', 'triangle', 'diamond', 'pin', 'arrow', 'none'
    * symbolSize 10/callback 标记大小 
    * large ：false 大数据量优化
    * coordinateSystem:该系列使用的坐标系，(bmap)地图
  5. effectScatter 带有涟漪特效动画的散点
    * coordinateSystem:该系列使用的坐标系，(bmap)地图
  6. radar 雷达图
    * data：[{}，{}，{}]
      * valve：
      * name：数据项名称 必须有
  7. map 地图。需要下载地图
    * roam :false 是否开启鼠标缩放和平移漫游
    * nameMap  自定义地区名称映射
      * {    'China' : '中国'}
      * mapValueCalculation 多个拥有相同地图类型的系列会使用同一个地图展现，如果多个系列都在同一个区域有值，ECharts 会对这些值统计得到一个数据。这个配置项就是用于配置统计的方式，目前有：'sum' 取和。'average' 取平均值。'max' 取最大值。'min' 取最小值。
    * itemStyle 地图区域的多边形 图形样式。
      * areaColor 地图区域的颜色。
      * color 图形的颜色。
    * data [{ name: '数据1',    value: 10},  
  8. funnel 漏斗图
    * gap漏斗层间间隔
    * sort ：排放顺序'ascending'，'descending'，'none'（表示按 data 顺序）或function
    * labelLine 标签的视觉引导线样式，label在left，right时伸出的一条线
    * funnelAlign 水平方向对齐
    * maxSize数据最大值 max 映射的宽度。

  9. gauge 仪表盘
    * detail仪表盘详情，用于显示数据。
    * axisTick 坐标轴小标记
    * axisLine 坐标轴线
    * splitLine 分隔线
       linestyle表示线条
    * axisLabel每个分割线对应的label
      可以是function 用switch
    * z 表示z轴
    * splitNumber: 11,仪表盘平分多少等份
    * radius: '50%',半径的长
    * title eg：km/h 不变化
    * detail 仪表盘详情，用于显示数据。
    * endAngle:45,结束角度45度，位于直角坐标系
    * startAngle: 135,开始角度135度，位于直角坐标系
    * pointer 指针
  10. candlestick 即我们常说的 K线图
  11. graph 关系图
  12. pictorialBar 象形柱图
    * symbol 图形类型。 还可以是图片路径
    symbolSize [,]图形大小
    symbolBoundingData 指定图形界限的值 图形的尺寸则由symbolBoundingData 决定。
    markLine 图表标线
    symbolClip  ：true：图形被剪裁后剩余的部分表示数值大小。
    symbolRepeat 指定元素是否可重复
    animationEasing ：elasticOut初始动画缓动效果
  13. custom 自定义
    * coordinateSystem:该系列使用的坐标系，(bmap)地图
  14. wordCloud词云
# setOption配置项
  1. title 标题组件，包含主标题和副标题
    * 居中用x:'center'
  2. legend 图例组件
    selectedMode 选择模式 'single' 或者 'multiple' 单选或者多选模式
  3. grid 直角坐标系内绘图网格，单个 grid 内最多可以放置上下两个 X 轴，左右两个 Y 轴。可以在网格上绘制折线图，柱状图，散点图（气泡图）。
    * shadowBlur 图形阴影的模糊大小。此配置项生效的前提是，设置了 show: true
  4. xAxis 直角坐标系 grid 中的 x 轴，默认类目型
    * boundaryGap 默认true 类似padding 给两边留空白
    * Gap 
    * type: 'value',
    * scale :true,脱离零刻度比例，可以不从零开始。设置max和min时无效
  5. yAxis 直角坐标系 grid 中的 y 轴，默认数值型 可以是数组型，有两个刻度
    type：value数值轴用于连续数据。；'category' 类目轴；'time' 时间轴，适用于连续的时序数据；'log' 对数轴。适用于对数数据
    name：
    axislabel:{formatter:'{value}ml'}坐标轴刻度
    gridIndex：x 轴所在的 grid 的索引，默认位于第一个 grid坐标系。
  6. dataZoom 组件 用于区域缩放，从而能自由关注细节的数据信息，或者概览数据整体，或者去除离群点的影响。
    * type:inside 鼠标滑轮进行缩放
    * type:slider 滑动条进行缩放
  7. toolbox 工具栏。内置有导出图片，数据视图，动态类型切换，数据区域缩放，重置五个工具。{
      * show ：是否显示工具栏；
      * feature Object各工具配置项。{
          magicType: //动态类型切换{
              type: ['line', 'bar', 'stack', 'tiled']
            }
          }
        dataView Object 数据视图工具，可以展现当前图表所用的数据，编辑后可以动态更新。
        restore Object 配置项还原。
        saveAsImage Object 保存为图片。
        * myTool1: { //自定义工具，以my开头
                show: true,
                title: '自定义扩展方法1',
                icon: 'path://M432.45,595',
                onclick: function (){
                    alert('myToolHandler1')
                }
            },
      }
    }
  8. tooltip 提示框组件。
    * formatter提示框浮层内容格式器，支持字符串模板和回调函数两种形式。
    * orient摆放方式：'vertical'：竖直放置。'horizontal'：水平放置。
    * data：总项目
    * selected：被选中显示的项目
    * axisPointer 坐标轴指示器配置项
      type ：'line' 直线指示器 cross' 十字准星指示器。'shadow' 阴影指示器 'none' 无指示器
  9. timeline 组件，提供了在多个 ECharts option 间进行切换、播放等操作的功能。
  10. series[i] 系列列表。每个系列通过 type 决定自己的图表类型，允许多个种类出现
    * seriesLayoutBy = 'column/row'；在设置dataset时改变默认维度名是第一行还是第一列,默认列
    * encode  可以定义 data 的哪个维度被编码成什么；encode: {
            x: [3, 1, 5],      // 表示维度 3、1、5 映射到 x 轴。
            y: 2,              // 表示维度 2 映射到 y 轴。
            tooltip: [3, 2, 4] // 表示维度 3、2、4 会在 tooltip 中显示。
        }
        // 地理坐标系（geo）特有的属性：
          encode: {
              lng: 3,
              lat: 2
          }
    * dimension  设置维度是个数组；数组中的每一项可以是：
      name 维度名 ；displayName如果没有指定，tooltip默认用name展示
      type：ordinal，对于类目；time，表示时间类型；number，默认，表示普通数据
      displayName: 一般用于 tooltip 中维度名的展示
  11. radar 只适合雷达 
    * name 每个指示器名称的配置项
    * indicator：[] 雷达图的指示器，用来指定雷达图中的多个变量（维度）
      { name: '销售（sales）', max: 6500},
      { name: '管理（Administration）', max: 16000, color: 'red'}, 
      * name 指示器名称
      * max/min 指示器最大最小值，可选
      * color 标签特定颜色
  12. visualMap是视觉映射组件，用于进行『视觉编码』，拉取显示值在区间范围内的对应的元素
    1. min 最小值
    2. max 最大值
    3. text:['High','Low'],上下显示的字
    4. calculable：true 拉动计算
    5. inRange在区间范围内
      color opacity……可选
    6. type: 'piecewise',分段视觉映射
    7.  pieces: [{ value: 0, color: COLORS[0] }, {gt: 900, lte: 1500},  // (900, 1500]设置区间段
    8. dimension ：2 表示2维
  13. dataset 可以是一个数组，通过datasetIndex:0引用；treemap、graph、lines 等，现在仍不支持在 dataset；echartsInstance. appendData接口提供了分片加载后增量渲染的能力，现在不支持 系列（series） 使用 dataset
     *  source 原始数据，一般来说是一个二维数组表
     *  dimensions 定义了series.data 或者 dataset.source 的每个维度的信息。在dataset。source第一行或列中指定，就不用了单独在dataset中指定或series.data中指定
     *   sourceHeader : true ;dataset.source 第一行/列是否是 维度名 信息。
     * 当使用了dataset时 可以在series中的 seriesLayoutBy = 'column/row'改变默认维度名是第一行还是第一列,默认列
  14. timeline.data ，提供了在多个 ECharts option 间进行切换、播放等操作的功能。中的每一项，对应于 options 数组中的每个 option。
#   line 折线/面积图
  1. stack string [ default: null ]  数据堆叠同个类目轴上系列配置相同的stack值后，后一个系列的值会在前一个系列的值上相加
  2. areaStyle Object 区域填充样式。（变为面积）
  3. label Object 图形上的文本标签，可用于说明图形的一些数据信息，比如值，名称等，
# 多图联动
  分别配置MYecharts1和mycharts2
  echarts.connect([MYecharts1,mycharts2])关联俩
# 自定义主题
  ECharts4 开始，除了一贯的默认主题外，新内置了两套主题，分别为 'light' 和 'dark' 
  下载主题，引入
  var mycharts=echarts。init(document.getElementById(''),'dark'//引入的主题)
  切换主题：先清除mycharts.clear()
          再从新定义 var mycharts=echarts。init(document.getElementById(''),'theam'
# 异步数据加载与更新
1. 方法一
  $(function(){
    var mycharts=echarts。init(docu……
    $.get(url).done(function(data){
      var option={

      }
      mycharts.setoption(option)
    })
  })
2. 方法二
  设置好option
  异步加载数据，通过操作dom填入option
# 异步加载数据更新加载提示
  mycharts.showLoading()//加载loading动画
  $.get(url).done(function(data){
    mycharts.hideLoading()//关闭loading动画
# 数据的动态更新
  把data数据单独用变量存放
  直接更新data数据
  清除之前的mychart.clear()
  重新设置option：mychart.setOption(option)
# 移动端自适应 Media Query
  option = {
    baseOption：{}，
    media：[{
            query: {...},   // 这里写规则。
            option: { },// 这里写此规则满足下的option,一般写布局有关
            },{} ]
      query:width、height、aspectRatio（长宽比）每个属性都可以加上 min 或 max 前缀
      option：legend:{}，series：[{radius:[],center:[]},{}]
      query优先级：同时满足都被 mergeOption，定义在后的后被 merge（即优先级更高）。
      默认 query：不写 query，所有规则都不满足时，采纳这个option。
      『复合 option』 即多次 setOption；中的 media 不支持 merge
# Echarts中的事件与行为
* 一般两种，用鼠标点击操作，hover图形时触发

    mychart.on('click',fun(params(){}))
      1. params当前点击图形元素的所有组件名称
    鼠标类型：click dbclick,mousedown,mousemove,mouseup,mouseover,mouseout
    encodeURIComponent()转码
   1. 如何区分鼠标点到了哪
    if(params.componentType==='markPoint')点到maek上
    if(params.componentType==='series'){//点到序列上
        if(params.dataType==='edge')  //点到边上
      }
  2. 通过点击分类异步获取更详细的分类的数据，从新渲染表格
    mychart.on('click',fun(params(){
      $.get(url).done(function(data){
        mycharts.setoption(option)
    }))
*     或使用可以交互组件后触发的行为
  legendselectchanged事件
  mychart.on('legendselectchanged',fun(params)){
    params.selected[params.name] //选中的元素名称
# 富文本
  type: 'scatter',//用散点类型
  data: [{value: [0, 0],位于坐标系的位置 通过调试xAxis和yAxis的max和min来控制它的位置
          label: {
                    normal: {
                        show: true,
                        formatter: ['{textBorder|textBorderColor + textBorderWidth}',
                        ].join('\n'),
                        rich: {//各处的 rich 属性中定义文本片段样式
                            textBorder: {//textBorder文本片段样式
                                fontSize: 20,
旋转label：先使用 align 和 verticalAlign 定位，再旋转。
文本片段的排版和对齐：每个文本片段，可以想象成 CSS 中的 inline-block，在文档流中按行放置。
# 使用SVG渲染
var chart = echarts.init(containerDom, null, {renderer: 'svg'});
常用版 和 完整版 已经包含了 SVG 渲染器，可直接使用。而 精简版 没有包括。
图表运行在低端安卓机，或者我们在使用一些特定图表如 水球图 等，SVG 渲染器可能效果更好
数据量很大、较多交互时，可以选用 Canvas 渲染器
# 无障碍访问
aria. show：true
#  ECharts GL 实现基础的三维可视化
npm install echarts-gl
 grid3D: {},
    // 默认情况下, x, y, z 分别是从 0 到 1 的数值轴
  xAxis3D: {},
  yAxis3D: {},
  zAxis3D: {}
# 人口迁徙图
1. 加载echarts相关组件
2. 准备DOM元素
3. 初始化echarts实例
4. 配置Echarts的option
  4.1 准备js相关变量
    var geoCoordMap ={'上海':[121.4648,31.2891],}地图上城市现实的经纬度
  4.2 模拟北京出发地到其他城市的模拟数据
    var BJData=[[{name:'北京'},{name:'上海’，value：95}],]出发地，目的地
  4.3 模拟出发地到各大目的地路线图
  var planpath=SVG画的矢量图
  4.4 用于转换特定数据
  var convertDara=function(data){
      var res=[]
      for(var i=0;i<data.length;i++){
        var dataItem=data[i];
        var fromCoord=geoCoordMap[dataItem[0].name];//出发地址信息
        var toCoord=geoCoordMap[dataItem[1].name];//到达地地址信息
        if (fromCoord&&toCoord){
          res.push([{
            name:dataItem[0].name,
            coord:fromCoord
          },{
            name:dataItem[1].name,
            coord:toCoord
          }])
        }
      }
      return res;
    }
  4.5 定义了svg画图时线条的颜色
  var color=[,,]
  4.6 图表系列
  var series=[ ]
  4.7  options
    geo:{
      map:'china',
      label:{
        emphasis:{show:false}
      },
      roam:true,

    }
  4.8 关于图表绘制内容的填充
  [['北京',BJData],[],[]].forEach((item,i)=>{
    //item:['北京',BJData] 取到北京的数据
    series.push({   
      name:item[0]+'top10',
      type:'lines',//用于起点到终点的路线绘制
      zlevel：1  用于 Canvas 分层谁大谁在上面
      effect：线特效的配置
        show :true 默认关闭
        period ：8 特效动画的时间，单位为 s。
        trailLength number[ default: 0.2 ]特效尾迹的长度。取从 0 到 1 的值，数值越大尾迹越长
        color 路线颜色
        symbolSize Array, number[ default: 3 ]特效标记的大小，
        lineStyle 现的样式
          curveness 边的曲度，支持从 0 到 1 的值，值越大曲度越大。
      data：convertDara(item[1])
    },{
        name:item[0]+'top10',
        type:'effectScatter',
        coordinateSystem :'geo',//坐标系使用地图
        zlevel：2,
        rippleEffect  ///涟漪特效相关配置。
          brushType：stroke  波纹的绘制方式
        symbolSize ：function(val){//特效大小
          //val接收data的值=[121.4648,31.2891,95}
          return val[2]/8
        }
        itemStyle:{
          nomal:{
            color:color[i]
          }
        },
        data:item[1].map(function(dataItem){
          return {
              name:dataItem[1].name,
              value:geoCoordMap[dataItem[1].name].concat([dataItem[1].valve]) 返回一个数组，坐标,dataItem[1].valve eg:(95)
          }
        })
    },{})
  })
# 热映电影排名分析
1. 引入echarts 
2. 准备容器
3. 初始化echarts
4. 关于echsrts option 的配置
*   var setData=(function(){})()相当于匿名函数，同时执行一次给setData     赋值，因为返回的是一个fun，所以setData是一个函数调用时加括号
    var setData=(function(){
      var option ={
        title:{},
        grid:{},定位坐标ltrd
        tooltip:{
          formatter:function(params){
            if (params.componentSubType=='pictorialbar'){
              return '电影'+params.name+'</br>豆瓣评分'+(params.value).toFixed(1)取小数点一位
            }
          }
        },
        xAxis:{data:[]},
        yAxis:{splitine:{show:false},axiseLine:{show:false}},
        series:[{
          type:'bar',
          barwidth:1,
          data:[],
          animationDelay :function(idx){// 延迟显示动画效果,idx条目的索引
            return idx*100;
          }
        },{
          type：'pictorialBar',
          symbolPosition:'end',图片现实的位置
          symbolRotate:165, 图片的角度
          symbolOffest:['50%','50%'],
          data:[],
          animationDelay:function(idx){
            reurn idx*100+500;
          }
        },{
          type:'graph',
          data:[{
            x y symbolSize :0            
          },{
            name:'btn',//按钮 圆形
            x:0,
            y:10,
            symbolSize：30
          }],
          itemStyle:{
            normal:{
              color borderColo borderWidth:1
            }
          }
        }]
      };
      var mark=1;
      return function(){
        var pics=[];
        var d=JSON.parse(localStorge.getItem('data'));
        ……
        if (mark%2==0){//从新排序return a-b 升序 b-a 降序
          pics.sort(function(a,b){
            return (mark/2|0)%2==0?(b.value-a.value):(a.value-b.value)
          })
        }，
        mark++
      }
    })()
    //如果本地缓存中有data数据，那么就用setData()方法给echsrts option赋值，如果没有，从服务器端请异步求加载数据，并把数据缓存到浏览器本地库中
*    if(localStorge.getItem('data')){
        setData();
      }else{
        $.ajax({
          type:'GET',
          uel:'',
          dataType:'jsonp',//跨域加载服务器数据
          success:function(data){
            localStorge.data=JSON.stringify(d),//将从服务器加载的数据缓存到DATA缓存中
            setData();
          }
        })
      }
*  实现给mychart图标点击时，得到当前电影对应的ID，跳转到对应的网站
    mychart.on('clicl',function(params){
      if(params.name=='btn'){
        setData();
      }else{
        windows.open('url')跳转网页
      }
    })
# 图标建议
比较： 
  基于分类：1变量：条形图，柱形图 2 变量 ：不等宽柱图 
  基于时间： 多属性：雷达图 曲线趋 单属性：柱形图，曲线图
    
分布：1个变量 直方图 正态分布 2 变量 散点 3变量 曲面图
构成：
  静态：饼图 
  随时间变化： 
    少周期： 仅增加差异 ：堆积百分比柱形图，相对和绝对差异：堆积柱形图
    多周期： 仅增加差异 增积百分比线积图 ，相对和绝对差异：增积线积图
联系： 2 变量：散点图 ；3变量 气泡图

1. 折线图：二维的大数据集 有点：容易反映出数据变化的趋势
2. 饼图 ：优势 明确表示数据比例情况，和渠道来源 缺点 ：不会具体数值
3. 地图：适用于空间位置的数据集，一般分为行政地图（气泡图，面积图）和GIS地图；行政地图有省份和城市数据就够了，GIS地图需要经纬度，细化到具体区域，只要有数据可做全区，全国和全球地图 
劣势：特殊情况下使用，涉及行政区
4. 雷达图：适用于多维数据（四维以上）一般用于表示某个数据字段的综合情况，6个点左右；优势：主要用来了解各项数据指标的变动情况及其好坏趋势
劣势，理解成本高
5. 漏斗图： 适用于业务流程多的流分析，显示个流程转化率；优势：网站分析中常用于转化率比较。不进能展示用户入网到购买的转化率，还能展现每一步的转化率，直观说明问题所在
缺点：单一漏斗图无法评价网站某个流程中各步骤转化率好坏
6. 词云 ： 使用场景：显示词频，可以用于用户头像，用户签名的工作；优势：很炫酷，很直观的表图 。使用场景单一，一般用于词频
7. 散点图： 使用场景：显示若干系列数据各值之间的关系。适用于三维数据集，但其中只有二位数据是需要比较的。另外，散点图还可以看出极值分布；优势：对极值分布和数据点的分簇区域（通过设置横纵辅助线，）散点图都很理想，如果数据非常多的点，那么散点图是最佳图表类型
劣势：在在点状图中显示多个序列看上去非常乱
8. 双轴线图：柱状图加折线图；数量级相差很大的情况，数据同环分析对比情况都合适。优势：特别通用，属于不同图标的组合使用，如柱+折结合，图标直观
# 可视化构成元素
形状 位置 尺寸 方向 色彩 纹理

option 表述了：数据、数据如何映射成图形、交互行为。
# 数据突出重点，突出用户关心的内容，要能够通过图标反映出数据的一个趋势，要能够从总结出对客户有用的信息；不能淡单纯的追寻美观；有效信息的传达，数据趋势的分析，根据客户的需求，在特定的场景下选择特定的具体的数据展示的方式，
数据可视化更多的是向客服表达的一个故事，背后呈现出来的是一个数据，数据本身不具有价值，把数据的规律找出来，把用户关心的点找到，并且有效的传达给用户，用户收到以后，可以根据这些点作出自己的决策，它才会有价值 。数据可视化本质上来讲就是给客户讲一个故事，这个故事希望情节跌宕起伏这样的一种趣味，否则对于用来将可能会很难会实现过目不忘的这个功能，看了之后没有什么感觉。如果你讲一个很好的故事的话他看玩这个可视化展现之后，他脑子里会有一个很深的印象，如果达到这个目的，可视化才算是非常成功的。所以他不是我们那种狭义的图表。在数据可视化工具tabel中，用图表组成仪表盘，用仪表盘组成故事，最终呈现的是一个完整的故事；故事+数据+设计=数据可视化
我们展示的东西，到底表达的是一个什么概念，通过展示的这样的一个内容，可以从中得到什么，什么时间什么地点发生了什么事。这件事发生完了后，你从这件事得到一个什么样的启发，这就是故事有价值的地方；故事是围绕数据来讲的，数据就是故事的内容，设计就是让故事变得非常的精彩，跌宕起伏。实际上是让图表更漂亮，色彩搭配，包括数据展现的一个角度等等