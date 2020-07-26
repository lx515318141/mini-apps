# 1.小程序介绍
## 1.1 什么是小程序
微信小程序，简称小程序，是一种不需要下载安装即可使用的应用，他实现了应用“触手可及”的梦想，用户扫一扫或搜一下即可打开应用。  
说明：  
1.小程序使用，扫一扫二维码或进入小程序  
2.小程序是需要下载的，小程序的占用大小很小，感觉不到下载  
3.2017年大小限制1M，目前大小限制2M（最终开发的小程序打包压缩后的大小）  
特点：  
1.免安装  
2.解决原生的app操作，基于微信开发  
3.使用必须在微信里面使用  

## 1.2 小程序的优点
1.方便快捷，即用即走。  
2.速度快，不占内存。  
3.安全稳定，保密性强。  
4.功能丰富，场景丰富。  
5.开发成本低，维护简便。  
6.体验好。  

## 1.3 小程序的运行平台环境
通常的应用开发需要适配安卓和iOS系统。但小程序只需要在微信中开辟出一小块内存，不需要对安卓和iOS系统进行适配。

## 1.4 小程序的注册流程
百度：微信公众号平台---进入平台---https://mp.weixin.qq.com/  

### 说明：  
1.自己不注册小程序吗？可以，不注册可以写小程序，自己的小程序不能发布，只能本地看。  
2.注册小程序，注册的是个人账号（部分API账号对个人不开放）  

### 流程：  
1.进入微信公众平台，在其中注册，注意这里一个邮箱只能注册一个微信产品，包括微信本身也是微信产品，如果邮箱和微信绑定了，则无法注册，所以我注册了一个新邮箱，注册完成之后是一系列激活。  
2.激活成功后需要填写小程序的相关信息：小程序名称。简称，头像，类目等（类目不要选游戏，模板不一样，可以用多个类目，且以及类目不可修改，二级可修改）。信息填写完成后可以点击查看，头像，名称，类目都可以修改，不过有次数限制，里面的APPID后面需要用到可以先考出来。  
3.添加项目成员，添加后权限可以都打开，添加的成员就可以看到你的代码，可以看效果等等。小程序发布以后添加体验成员可以通过扫描二维码进行小程序的测试。  
4.发布新闻无法发布。  

### 下载、安装开发工具  
在小程序开发流程里可以下载普通小程序开发工具，工具页面下面概述下面有一个微信开发者工具，下载稳定版，然后安装。安装完成后，打开小程序开发工具，需要微信扫码登录，选择小程序，新建项目，项目名称可改，目录选择一个空目录，APPID用刚刚从小程序开发流程里面复制出来的，开发模式选小程序，后台服务根据实际情况选择，第一次的demo没有使用云服务。最后点击新建。

## 1.5 了解编辑器
开发者工具编译界面分三个模块，左侧是模拟器，右侧为代码区，代码区下面是调试区。可通过左上角的开关控制三个区域的打开和关闭。可以同时打开多个开发者工具。  
使用测试号和APPID的区别是使用APPID可以将代码上传到微信公众平台的库里面，而使用测试号不行，也无法通过公众平台发布。  
测试是尽量使用真机测试功能。APPID也是可以更改的。  
使用APPID的可以进行上传，上传就是进行发布，点击上传就会将本地代码进行压缩，并上传到微信公众平台，如果以及上传过一次，再次上传会将之前的替换掉，上传需要填写版本号，项目备注（如进行了哪些修改，哪些更新等等）。上传后可在微信公众平台查看，找到项目管理，可以看到项目分为几个版本，开发版、审核版、线上版。  
开发版是还在制作中的版本，开发版上传的都是体验版，需要测试人员进行测试（体验版可以设置开关，取消体验版就不会生成体验版，不会有二维码供人扫描测试。选为体验版就可以点击生成二维码进行测试。）代码和测试都没有问题了，可以进行提交，提交给微信团队，提交过程中需要根据提示对小程序的相关信息进行补充，提交完之后就会进入到审核版。  
审核版提交之后一般一致两日就会出结果，会通过微信和邮箱通知你审核通过或是不通过，不通过会告知不通过的原因。通过之后点击按键就会进行发布进入线上版。  

## 1.6 小程序的目录结构
根目录中含有两个目录，分别为：page，utils；以及一些文件包括：app.js、app.json、app.wxss、project.config.json、setmap.json（前三个文件为小程序的应用配置或全局配置）。  
app.js（负责写逻辑）、app.json（负责写配置项）、app.wxss（负责写样式）、project.config.json（负责写项目的配置参数的描述，如：项目的APPID，使用的ES6的版本，小程序的库的版本，编辑器的设置过的配置参数）、setmap.json（负责写搜索，如制定小程序内那些页面可以配搜索）

### page
page页面主要存放页面，默认是存在两个页面，index和logs，这两个也是目录，每个目录内部包含四个文件，即小程序的一个页面由四个文件组成分别为.js、.json、.wxml、.wxss，在一个目录内部，这四个文件的名字要一致，一般和目录同名。  
如：index.js、index.json、index.wxml、index.wxss  
这样便于引用，而且每个页面的样式和逻辑不需要用link和script引入。  

### utils
utils中的utils.js中存放点击头像跳转到日志也没时获取到当前时间的一个功能性函数。

## 1.7 具体文件介绍
### setmap.json
setmap.json中可以设置哪些页面会被微信搜索到，哪些页面不会被微信搜索到，在该文件中有小程序的文档的链接，可以仔细阅读十分重要。setmap.json中的各个参数使用说明可参看小程序文档中：配置小程序->全局配置->小程序全局配置（蓝色字的链接）  
app.json用来对小程序进行全局配置，决定页面文件的路径、窗口表现、设置网络超时时间、设置多个tab等。  
app.json中的各种类型：

#### page 
1.写入page中各个页面的路径,在第一个位置的路径是首页。  
2.文件中的string必须使用双冒号，路径中文件的后缀名省略。  
3.各路径间用逗号分隔，最后一个路径后面没有逗号。  
4.json中不能加注释。
```
"pages":[
    "pages/index/index",
    "pages/logs/logs"
  ]
```

#### window
window注意负责设置小程序的导航栏、状态栏、标题、窗口背景颜色等，具体设置的属性名参看小程序文档中的小程序全局配置。
```
"window": {
    "navigationBarBackgroundColor": "#fff",     // 导航栏背景色
    "navigationBarTitleText": "WeChat",         // 导航栏标题文字内容
    "navigationBarTextStyle": "black",          // 导航栏标题颜色，仅支持 black/white
    "backgroundTextStyle": "light",             // 下拉 loading 的样式，仅支持 dark/light
    "backgroundColor": "#fffff",                // 窗口的背景色（不过背景色一般看不到，会被页面的颜色挡住，只有下拉时才能看到）
    "backgroundTextStyle": "#fffff",            // 下拉 loading 的样式，仅支持 dark/light
    "enablePullDownRefresh": "true/false",      // 是否开启全局的下拉刷新。详见 Page.onPullDownRefresh
  }
```
这里设置的各种样式是全局的，各个页面共享这个样式。各个页面的json也是进行样式设置，且优先级高于全局中设置的样式，即局部高于全局。且页面中的json只有窗口样式，即只有window属性。

### page
page中放小程序的页面，想添加新页面，现在page中创建目录，右键点击目录选择创建page，然后使用和心简单的目录一样的名字，回车，就会同步创建四个文件，并且在app.json的pages中也会自动生成该页面的路径。删除时也需要同步删除，即删除文件夹的同时删除app.json中的页面路径。  

## 1.8逻辑层和界面层——tabBar
如果小程序是一个多 tab 应用（客户端窗口的底部或顶部有 tab 栏可以切换页面），可以通过 tabBar 配置项指定 tab 栏的表现，以及 tab 切换时显示的对应页面。  
其中 list 接受一个数组，只能配置最少 2 个、最多 5 个 tab。tab 按数组的顺序排序，每个项都是一个对象，其属性值如下：  

## 1.9 组件
### view
`<view></view>`块级元素，可嵌套view，和其他元素，类似div。

### swiper
滑块视图容器。其中只可放置swiper-item组件，否则会导致未定义的行为。
```
<swiper>
  <swiper-item>slide1</swiper-item>
  <swiper-item>slide2</swiper-item>
  <swiper-item>slide3</swiper-item>
</swiper>
```
添加在swiper上的常用属性：
indicator-dots='true/false'       是否显示面板指示点  
indicator-color='rgba'            指示点颜色  
indicator-active-color='#000000'  当前选中指示点颜色  
autoplay='true/false'             是否自动播放  
current='0'                       当前所在滑块的index  
interval='5000'                   自动切换时间间隔（毫秒）  
duration='500'                    滑动动画时长  
circular='true/false'             是否采用衔接滑动（即是否无缝）  
vertical='true/false'             滑动方向是否为纵向  
...

### scroll-view
可滚动视图区域。使用竖向滚动时，需要给scroll-view一个固定高度，通过 WXSS 设置 height。组件属性的长度单位默认为px，2.4.0起支持传入单位(rpx/px)。  
注意：  
1.scroll-view中的元素要一行显示，不能换行，溢出隐藏
2.scroll-view中包含的组件的display:inline-block;
```
<scroll-view>
  <text>导航1</text>
  <text>导航2</text>
  <text>导航3</text>
  <text>导航4</text>
  <text>导航5</text>
  <text>导航6</text>
  <text>导航7</text>
<scroll-view>
```
添加在scroll-view中的常用属性：  
scroll-x='true/false'              允许横向滚动
scroll-y='true/false'              允许纵向滚动
...

### 文本
```
<text>行内元素</text>
<text>行内元素</text>
```

### 进度条
```
<progess percent='20' show-info></progress>           // 显示数值
<progess percent='20'stroke-width='6'></progress>      // 进度条宽度
<progess percent='20' active></progress>              // 动画效果
```

### 图表icon
```
<icon type='success'></icon>
<icon type='success' size='30'></icon>
<icon type='success' color='pink'></icon>
```

### 表单
button按钮
```
// button按钮功能十分强大，而且可以通过css对其样式进行修改
// 如果无法修改样式，是因为自己写的权重不够，可以用!important增加权重
<button size='mini'>按钮</button>           // 修改按钮大小
<button type='primary'>按钮</button>        // 修改按钮样式类型，只有三个合法值：primary(绿色)，default(白色)，warn(红色)
<button disabled='true'>按钮</button>       // 是否禁用
<button loading='true'>按钮</button>        // 名称前是否带 loading 图标
<button open-type='share'>转发</button>     // 转发微信
```

input输入框默认是没有边框的，如果需要边框，需要自己手动添加css
`<input type='text' placeholder='请输入搜索的内容'></input>`

### 媒体组件
audio：音频。1.6.0版本开始，该组件不再维护。建议使用能力更强的 wx.createInnerAudioContext 接口。API和HTML的audio标签的API类似。
image：小程序中使用image除非用来做icon，否则必须设置大小，不然就会按照系统默认设置为 width: 320px; height: 240px; 。将图片放入轮播的时候，因为轮播也要自己默认的大小，为了和图片契合，也要进行修改。
```
<image src='../../image/home.png'><image>
```

### 导航
navigator：是块级元素，所以可以装image，button等元素都可以。
```
<navigator url='../newsDetail/newsDetail'>信息列表---11---进入新闻详情</navigator>
```
navigator常用属性：  
url='路径'                 // 必选，跳转路径
open-type='navigator'      // 跳转方式，很重要
open-type的值：
1.navigator：对应 wx.navigateTo 或 wx.navigateToMiniProgram 的功能（保留当前页面，跳转到应用内的某个页面。但是不能跳到 tabbar 页面。使用 wx.navigateBack 可以返回到原页面。小程序中页面栈最多十层）
2.redirect：对应 wx.redirectTo 的功能（关闭当前页面，跳转到应用内的某个页面。但是不允许跳转到 tabbar 页面）
3.switchTab：对应 wx.switchTab 的功能（跳转到 tabBar 页面，并关闭其他所有非 tabBar 页面）
4.reLaunch：对应 wx.reLaunch 的功能（关闭所有页面，打开到应用内的某个页面，也可以跳到tabBar）
5.navigateBack：对应 wx.navigateBack 的功能（关闭当前页面，返回上一页面或多级页面。可通过 getCurrentPages 获取当前的页面栈，决定需要返回几层）
6.exit：退出小程序，target="miniProgram"时生效

# 2.小程序的JS和逻辑
## 2.1 逻辑层和渲染层
### 小程序的宿主环境
我们称微信客户端给小程序所提供的环境为宿主环境。小程序借助宿主环境提供的能力，可以完成许多普通网页无法完成的功能。  
小程序开发框架的目的是通过尽可能简单、高效的方式让开发者可以在微信中开发具有原生APP体验的服务。  
整个小程序框架系统分为两部分：逻辑层（App Service）和视图层（View）

### 逻辑层与渲染层分离
逻辑层：由JS完成的业务数据供给界面事件处理。
渲染层：页面结构（WXML）页面样式（WXSS）展示逻辑层的数据
首先我们来简单的了解下小程序的运行环境。小程序的运行环境分为渲染层和逻辑层，其中WXML模板和WXSS样式工作在渲染层，JS脚本工作在逻辑层。  
小程序的渲染层和逻辑层分别由2个线程管理：渲染层的界面使用了WebView 进行渲染；逻辑层采用JsCore线程运行JS脚本。一个小程序存在多个界面，所以渲染层存在多个WebView线程，这两个线程的通信会经由微信客户端（下文中也会采用Native来代指微信客户端）做中转，逻辑层发送网络请求也经由Native转发，小程序的通信模型下图所示。

## 2.1 生命周期、全局变量使用
### xxx.js
绑定生命周期回调函数、错误监听和页面不存在监听函数
#### 1.app.js存放小程序全局逻辑
生命周期回调函数：小程序从创建到消失的整个过程产生的一些自定义的函数。
onLaunch：小程序加载时触发，只会触发一次，在首次进入小程序时触发。
onShow：小程序显示或后台切入前台时触发
onHide：页面隐藏或切入后台时触发
onError：错误监听函数

globalData全局变量：页面共享的值。

#### 2.每个小程序的页面都有js文件，存放当前的页面逻辑，每个页面的js也有生命周期函数（data页面的数据，生命周期，自定义函数）
页面中的生命周期：
onLoad：页面加载时触发，一个页面只会调用一次，可以在onLoad的参数中获取打开当前页面路径中的参数
onShow：页面显示/切入后台时触发
onReady：页面初次渲染完成时触发。一个页面只会调用一次，代表页面以及准备妥当，可以与视图层进行交互。
onHide：页面隐藏/切入后台时触发，如navigateTo或底部tab切入其他页面，小程序切入后台等。
onUnload：页面卸载时触发。如redirectTo或navigateBack到其他页面。
onPullDownRefresh：监听下拉动作
onRechBottom：页面上拉触发底部事件的处理函数
onShareAppMessage：用户点击右上角分享

#### 3.globalData全局变量：所有页面共享的值  
开发者可通过 getAPP 方法获取到全局唯一的 APP 实例
```
var app = getApp();
console.log(app.globalData.xxx)
```

#### 4.小程序里面没有DOM
```
console.log(window, 'window');  // undefined
console.log(document, 'DOM');   // undefined
```

#### 5.模块--功能块
封装的方法，在外边可以被被所有的页面调用。小程序中的模块封装和引入是学习node.js规范，通过使用Common.js来使用。
步骤：  
a.外部定义的方法，需要暴露出接口
```
// 可以在utils目录中创建模块（如fun.js），创建的方法一定是会多次使用功能性函数，公共方法。
function fun(){
  var a = 123;
  var b = 456;
  return a+b;
}

// 加上模块中有多个对象或函数
var obj = {
  name: 'haha',
  age: 20
}

// 需要暴露出去
// 1.直接暴露函数名（此方法只能导出一个函数）
module.exports = fun;

// 2.直接暴露对象{demo(变量名):fun,...}（因为导出的是对象，此方法可导出多个函数）
module.exports.demo = fun;  // {demo:fun}

// 3.暴露多个函数，对象
module.exports = {
  fun:fun,
  obj:obj
}
```
b.哪里使用哪里调用外部方法，模块可以是页面用，也可以是app.js用。
```
// 使用外部的js方法，引入进来
// 语法：var 变量 = require('js相对路径.js')
var fun = require('utils/fun.js')

// 第一种导出方法的使用方式
console.log(fun)  // 打印出来的是函数体
var value = fun()

// 第二种导出方法的使用方式
console.log(fundemo)  // 打印出来的是函数体
var value = fun.demo()

// 第三种导出放的使用与第二种类似

// 此时打印的是函数的返回值，上面调用函数时可以传参进去，具体视函数功能而定。
console.log(value)
```

## 2.2 数据绑定
WXML中的动态数据均来自对应的Page的data。
### 简单绑定
1.双大括号绑定数据 {{变量}}
2.数据绑定语法可以写在属性里面，即写在双大括号里面的东西，既可以做内容们也可以做属性
3.特殊：用于checkbox组件（多选框），当此标签的checked为true时为选中，为false时为未选中，但直接写false会不识别仍然显示已选中，所有需要配合{{变量}}次语法使用。
示例：
```
// Page的WXML
<view>{{ msg }}<view>
// 写在属性里面
<view class="box {{active}}">{{ msg }}<view>
// 特殊
<checkbox checked='{{false}}'>吃西瓜</checkbox>

// Page的js
Page({
  data: {
    msg: 'Hello World',
    active: 'active'
  }
})

// Page的WXSS中
.active{
  background: pink;
}
```

## 2.3 列表渲染
### 1.列表渲染wx:for
在组件上使用wx:for控制属性绑定一个数组，即可使用数组中各项的数据重复渲染该组件。默认数组的当前项的下标变量名默认为index，数组当前项的变量名默认为item
```
// Page的WXML
// 语法：wx:for='{{数组名}}' index下标 item数组遍历的每一项的值 
// 组件内要加一个wx:key='index'，和vue中:key='index'功能是类似的，防止数据发生动态变化，而导致渲染出问题，即为了提高渲染效率。
// 不加会有警告，如果确定数据不是动态的，可以不加
<view>
  <text wx:for='{{arr}}' wx:key='index'>{{item}}---{{index}}</text>
</view>

// Page的js
Page({
  data:{
    arr:[10,20,30,40,'hellow','今天你开心吗？']
  }
})
```

### 2.修改每一项变量名和下标名
使用wx:for-item可以指定数组当前元素的变量名
使用wx:for-index可以指定数组当前下标的变量名
```
<view wx:for='{{arr}}' wx:key='index'>{{item}}--下标:{{index}}<view>
<view wx:for='{{arr}}' wx:for-item='itemVal' wx:for-index='i' wx:key='index'>{{itemVal}}--下标:{{i}}<view>
```
注意：一般情况item和index不会去修改，当使用wx:for遍历数据，有两层嵌套的时候，才需要修改item和index。

### 3.列表渲染数组wx:for='' 数组为复杂类型，如：[{},{},{},...]
```
Page({
  data:{
    books:[
      {
        id:1,
        bookName:'三国演义',
        price:20
      },
      {
        id:2,
        bookName:'水浒传',
        price:30
      },
      {
        id:3,
        bookName:'西游记',
        price:40
      },
      {
        id:4,
        bookName:'红楼梦',
        price:50
      }
    ]
  }
})

<view wx:for='{{books}}' wx:key='index'>{{item.bookName}}——价格{{item.price}}</index>
```