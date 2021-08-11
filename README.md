# 一、html

## 1、html语义化
定义：语义化是根据内容结构化（内容语义化），选择合适的标签（代码语义化），便于开发者阅读和写出更优雅代码的同时，让浏览器的爬虫和机器更好的解析

作用：<br />
1、有利于SEO，有助于爬虫抓取更多的有效信息，爬虫是依赖于标签来确定上下文和各个关键字的权重<br />
2、语义化的HTML在没有CSS的情况下也能呈现较好的内容结构与代码结构<br />
3、方便其他设备的解析<br />
4、便于团队开发和维护<br />

注意：<br />
1、尽可能少的使用无语义的标签 div 和 span<br />
2、在语义不明显时，既可以使用 div 或者 p 时，尽量用 p, 因为 p 在默认情况下有上下间距，对兼容 特殊终端有利<br />
3、不要使用纯样式标签，如:b、font、u 等，改用 css 设置<br />
4、需要强调的文本，可以包含在 strong 或者 em 标签中(浏览器预设样式，能用CSS 指定就不用他 们)，strong 默认样式是加粗(不要用 b)，em 是斜体(不用i)<br />
5、使用表格时，标题要用 caption，表头用 thead，主体部分用 tbody 包围，尾部用 tfoot 包围。表 头和一般单元格要区分开，表头用 th，单元格用 td<br />
6、表单域要用 fieldset 标签包起来，并用 legend 标签说明表单的用途<br />
7、每个 input 标签对应的说明文本都需要使用 label 标签，并且通过为 input 设置id 属性，在 lable 标签中设置 for=someld 来让说明文本和相对应的 input 关联起来<br />

html5新标签:<br />
1、article: 定义文档内的文章<br />
2、footer: 页脚<br />
3、header: 页眉<br />
4、section: 定义文档中的章节<br />
5、dialog: 定义对话框或窗口<br />
6、canvas: 可被用来通过JavaScript（Canvas API 或 WebGL API）绘制图形及图形动画

## 2、canvas相关
使用前需先获得上下文环境，暂不支持3d

常用api：<br />
1、fillRect(x, y, width, height)实心矩形<br />
2、strokeRect(x, y, width, height)空心矩形<br />
3、fillText('杀死那个河南人'，200, 200)实心文字<br />
4、strokeRect('杀死那个河南人', 200, 200)空心文字<br />

新版本兼容低版本:<br />
1、ie9 之前版本通过 createElement 创建 html5 新标签<br />
2、引入 html5shiv.js

## 3、svg和canvas的区别
1、canvas是h5提供的新的绘图方法<br />
2、svg已经有了十多年的历史 canvas画图基于像素点，是位图，如果进行放大或缩小会失真<br />
3、svg基于图形，用html标签描绘形状，放大缩小不会失真<br />
4、canvas需要在js中绘制，svg在html绘制<br />
5、canvas支持颜色比svg多<br />
6、canvas无法对已经绘制的图像进行修改、操作，svg可以获取到标签进行操作<br />

## 4、html5新特性
HTML5主要是关于图像，位置，存储，多任务等功能的增加。<br />
1、拖拽释放(Drag and drop) API<br />
2、语义化更好的内容标签(header,nav,footer,aside,article,section) 音频、视频API(audio,video) <br />
3、画布(Canvas) API<br />
4、地理(Geolocation) API<br />
5、本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失; sessionStorage 的数据在浏览器关闭后自动删除<br />
6、表单控件，calendar、date、time、email、url、search<br />

## 5、如何处理HTML5新标签的浏览器兼容问题
IE8/IE7/IE6支持通过document.createElement方法产生的标签，可以利用这一特性让这些浏览器支持 HTML5新标签，当然最好的方式是直接使用成熟的框架、使用最多的是html5shim框架

## 6、说说 title 和 alt 属性
1、两个属性都是当鼠标滑动到元素上的时候显示<br />
2、alt 是 img 的特有属性，是图片内容的等价描述，图片无法正常显示时候的替代文字。<br />
3、title 属性可以用在除了base，basefont，head，html，meta，param，script和title之外的所有标签，是对dom元素的一种类似注释说明

## 7、HTML全局属性(global attribute)有哪些
class :为元素设置类标识<br />
data-* : 为元素增加自定义属性<br /> draggable : 设置元素是否可拖拽<br /> id : 元素 id ，文档内唯一<br />
lang : 元素内容的的语言<br />
style : 行内 css 样式<br />
title : 元素相关的建议信息<br />

## 8、

# 二、CSS

## 1、让一个元素水平垂直居中，到底有多少种方案?
![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9be20622ddef4d59b953c3c8f45930e9~tplv-k3u1fbpfcp-watermark.image)

## 2、浮动布局的优点?有什么缺点?清除浮动有哪些方式?
### 浮动布局简介
当元素浮动以后可以向左或向右移动，直到它的外边缘碰到包含它的框或者另外一 个浮动元素的边框为止。元素浮动以后会脱离正常的文档流，所以文档的普通流中的框就变现的好 像浮动元素不存在一样。

### 优点
这样做的优点就是在图文混排的时候可以很好的使文字环绕在图片周围，因为浮动元素会脱离网页文档，与其他元素发生重叠，但是，不会与文字内容发生重叠。另外当元素浮动了起来之后， 它有着块级元素的一些性质例如可以设置宽高等，但它与inline-block还是有一些区别的，第一个就是关 于横向排序的时候，float可以设置方向而inline-block方向是固定的;还有一个就是inline-block在使用 时有时会有空白间隙的问题

### 缺点
最明显的缺点就是浮动元素一旦脱离了文档流，就无法撑起父元素，会造成父级元素高度塌陷。

### 清除浮动的方式
#### 1）添加额外标签
```js
<div class="parent"> //添加额外标签并且添加clear属性
  <div style="clear:both"></div> //也可以加一个br标签
</div>
```
#### 2）父级添加overflow属性，或者设置高度
```js
<div class="parent" style="overflow:hidden">//auto 也可以 //将父元素的overflow设置为hidden
  <div class="f"></div>
</div>
```
#### 3）建立伪类选择器清除浮动(推荐)
```js
//在css中添加:after伪元素
.parent:after {
/* 设置添加子元素的内容是空 */
  content: '';
/* 设置添加子元素为块级元素 */
  display: block;
/* 设置添加的子元素的高度0 */
  height: 0;
/* 设置添加子元素看不见 */
  visibility: hidden;
/* 设置clear:both */
  clear: both;
}
<div class="parent">
    <div class="f"></div>
</div>
```
## 3、使用display:inline-block会产生什么问题?解决方法?
### 问题复现
问题: 两个display:inline-block元素放到一起会产生一段空白。 <br>
如代码:
```js
<!DOCTYPE html>
<html lang="en">
  <head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0"> <meta http-equiv="X-UA-Compatible" content="ie=edge"> <title>Document</title>
<style>
.container { width: 800px; height: 200px;
}
.left {
font-size: 14px; background: red; display: inline-block; width: 100px;
height: 100px;
}
.right {
font-size: 14px; background: blue; display: inline-block; width: 100px;
height: 100px;
}
    </style>
  </head>
<body>

 
<div class="container">
  <div class="left">
左
</div><div class="right"> 右
  </div>
</div>

<div class="container">
      <div class="left">
左
      </div>
      <div class="right">
右
      </div>
    </div>
  </body>
</html>
```
效果如下:<br>

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9986e69276e947cbb5ee577a29b51337~tplv-k3u1fbpfcp-watermark.image)

### 产生空白的原因
元素被当成行内元素排版的时候，元素之间的空白符(空格、回车换行等)都会被浏览器处理，根据 CSS中white-space属性的处理方式(默认是normal，合并多余空白)，原来HTML代码中的回车换行被 转成一个空白符，在字体不为0的情况下，空白符占据一定宽度，所以inline-block的元素之间就出现了空隙。
### 解决办法 
#### 1）将子元素标签的结束符和下一个标签的开始符写在同一行或把所有子标签写在同一行

```js
<div class="container">
  <div class="left">
左
</div><div class="right"> 右
  </div>
</div>
```
#### 2）父元素中设置font-size: 0，在子元素上重置正确的font-size

```js
.container{ width:800px; height:200px; font-size: 0;}
```

#### 3）为子元素设置float:left

```js
.left{
float: left; font-size: 14px; background: red; display: inline-block; width: 100px;
height: 100px;
} //right是同理
```

## 4、布局题:div垂直居中，左右10px，高度始终为宽度一半
问题描述: 实现一个div垂直居中, 其距离屏幕左右两边各10px, 其高度始终是宽度的50%。同时div
中有一个文字A，文字需要水平垂直居中。
### 思路一:利用height:0; padding-bottom: 50%;

```js
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        html,
        body {
            height: 100%;
            width: 100%;
        }

        .outer_wrapper {
            margin: 0 10px;
            height: 100%;
            /* flex布局让块垂直居中 */
            display: flex;
            align-items: center;
        }

        .inner_wrapper {
            background: red;
            position: relative;
            width: 100%;
            height: 0;
            padding-bottom: 50%;
        }

        .box {
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 20px;
        }
    </style>
</head>

<body>
    <div class="outer_wrapper">
        <div class="inner_wrapper">
            <div class="box">A</div>
        </div>
    </div>
</body>

</html>
```
#### 强调两点:
##### 1）padding-bottom究竟是相对于谁的?
答案是相对于 父元素的width值 。
那么对于这个out_wrapper的用意就很好理解了。 CSS呈流式布局，div默认宽度填满，即100%大小，
给out_wrapper设置margin: 0 10px;相当于让左右分别减少了10px。 
##### 2）父元素相对定位，那绝对定位下的子元素宽高若设为百分比，是相对谁而言的?
相对于父元素的(content + padding)值, 注意不含border 延伸:如果子元素不是绝对定位，那宽高设为百分比是相对于父元素的宽高，标准盒模型下是
content, IE盒模型是content+padding+border。

### 思路二: 利用calc和vw

```js
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style>
        * {
            padding: 0;
            margin: 0;
        }

        html,
        body {
            width: 100%;
            height: 100%;
        }

        .wrapper {
            position: relative;
            width: 100%;
            height: 100%;
        }

        .box {
            margin-left: 10px;
            /* vw是视口的宽度， 1vw代表1%的视口宽度 */
            width: calc(100vw - 20px);
            /* 宽度的一半 */
            height: calc(50vw - 10px);
            position: absolute;
            background: red;
            /* 下面两行让块垂直居中 */
            top: 50%;
            transform: translateY(-50%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
        }
    </style>
</head>

<body>
    <div class="wrapper">
        <div class="box">A</div>
    </div>
</body>

</html>
```

# 三、javascript




# 四、框架

- React


- Vue


# 五、Typescript




# 六、算法
## 1、两个数不使用四则运算得出和

1)按位与<br>
8 & 7 // -> 0<br>
// 1000 & 0111 -> 0000 -> 0<br>
每一位都为 1，结果才为 1<br>
2)按位或<br>
8 | 7 // -> 15<br>
// 1000 | 0111 -> 1111 -> 15<br>
其中一位为 1，结果就是 1<br>
3)按位异或 每一位都不同，结果才为 1<br>
8 ^ 7 // -> 15<br>
8 ^ 8 // -> 0<br>
// 1000 ^ 0111 -> 1111 -> 15 // 1000 ^ 1000 -> 0000 -> 0<br>
从以上代码中可以发现按位异或就是不进位加法<br>

这道题中可以按位异或，因为按位异或就是不进位加法，8 ^ 8 = 0 如果进位了，就是 16 了，所以我们只需要将两个数进行异或操作，然后进位。那么也就是说两个二进制都是 1 的位置，左边应该有一个 进位 1，所以可以得出以下公式 a + b = (a ^ b) + ((a & b) << 1) ，然后通过迭代的方式模拟加法

答案：

```js
function sum(a, b) {<br>
    if (a == 0) return b<br>
    if (b == 0) return a<br>
    let newA = a ^ b<br>
    let newB = (a & b) << 1<br>
    return sum(newA, newB)<br>
}
```


## 2、冒泡排序
冒泡排序的原理如下，从第一个元素开始，把当前元素和下一个索引元素进行比较。如果当前元素大， 那么就交换位置，重复操作直到比较到最后一个元素，那么此时最后一个元素就是该数组中最大的数。 下一轮重复以上操作，但是此时最后一个元素已经是最大数了，所以不需要再比较最后一个元素，只需 要比较到 length - 1 的位置。

```js
function checkArray(array) {
  if (!array || array.length <= 2) return
}

function swap(array, left, right) {
  let rightValue = array[right]
  array[right] = array[left]
  array[left] = rightValue
}

function bubble(array) {
  checkArray(array);
  for (let i = array.length - 1; i > 0; i--) {
    // 从 0 到 `length-1` 遍历
    for (let j = 0; j < i; j++) {
      if (array[j] > array[j + 1]) swap(array, j, j + 1)
    }
  }
  return array;
}
```
时间复杂度: 等差数列，去掉常数项后为O(n*n)

## 3、插入排序
![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/bac913cbf21b4f0c80011b0706d55293~tplv-k3u1fbpfcp-zoom-1.image)
有点像冒泡排序的逆向操作。冒泡排序是从最后一个开始排，插入排序是从第一个开始排

冒泡排序的原理如下，从第一个元素开始，把当前元素和下一个索引元素进行比较。如果当前元素大， 那么就交换位置，重复操作直到比较到最后一个元素，那么此时最后一个元素就是该数组中最大的数。 下一轮重复以上操作，但是此时最后一个元素已经是最大数了，所以不需要再比较最后一个元素，只需 要比较到 length - 1 的位置。

```js
function checkArray(array) {
  if (!array || array.length <= 2) return
}

function swap(array, left, right) {
  let rightValue = array[right]
  array[right] = array[left]
  array[left] = rightValue
}

function sort(arr) {
  for(let i = 1; i < arr.length; i++) {
    for(let j = i -1; j >= 0 && arr[j] > arr[j + 1]; j--) {
      swap(arr, j, j + 1)
    }
  }
  return arr
}
```
时间复杂度: 等差数列，去掉常数项后为O(n*n)

## 4、选择排序
![image.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1309f3e3f03744238d93a50a62b5de15~tplv-k3u1fbpfcp-zoom-1.image)
### 选择排序的原理
遍历数组，设置最小值的索引为 0，如果取出的值比当前最小值小，就替换最小 值索引，遍历完成后，将第一个元素和最小值索引上的值交换。如上操作后，第一个元素就是数组中的 最小值，下次遍历就可以从索引 1 开始重复上述操作。

```js
function selection(array) { checkArray(array);
for (let i = 0; i < array.length - 1; i++) {
let minIndex = i;
for (let j = i + 1; j < array.length; j++) {
      minIndex = array[j] < array[minIndex] ? j : minIndex;
    }
    swap(array, i, minIndex);
  }
  return array;
}
```
时间复杂度: 等差数列，去掉常数项后为O(n*n)



# 七、小程序

# 八、浏览器

## 1、浏览器每帧执行动作

-   首先需要处理输入事件，能够让用户得到最早的反馈；

-   接下来是处理定时器，需要检查定时器是否到时间，并执行对应的回调；

-   接下来处理 Begin Frame（开始帧），即每一帧的事件，包括 window.resize、scroll、media query change 等；

-   接下来执行请求动画帧 requestAnimationFrame（rAF），即在每次绘制之前，会执行 rAF 回调；

-   紧接着进行 Layout 操作，包括计算布局和更新布局，即这个元素的样式是怎样的，它应该在页面如何展示；

-   接着进行 Paint 操作，得到树中每个节点的尺寸与位置等信息，浏览器针对每个元素进行内容填充；

-   到这时以上的六个阶段都已经完成了，接下来处于空闲阶段，可以在这时执行 requestIdleCallback 里注册的任务；

## 2、

