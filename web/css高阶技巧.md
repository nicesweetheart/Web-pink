# 一.学习内容

## 1.精灵图

### CSS精灵技术

目的：减少服务器接受请求次数，提高页面加载速度



此处因为没有精灵图软件所以未写，周一找台windows，补出来



## 2.字体图标

### 2.1实质

展示的是图标，实质是字体



### 2.2优点

（1）轻量化：字体比图标小

（2）灵活性：本质是字体，可以随便修改颜色

（3）兼容性：兼容所有浏览器

### 2.3下载

Icomoon字体库:https://icomoon.io/

Alibaba字体库：https://www.iconfont.cn/

### 2.4导入步骤

1.把fonts文件夹放到页面的根目录下（fonts下四个文件是因为兼容性问题）

2.将字体文件引入到css中（）将icomoon文件夹中的style.css文件中的font face引入到自己的css中

3.打开icmoon文件夹中的html，将字体图标中的小方块复制到html文件中

4.为字体图标文件书写样式，写入font-family：”icomoon“



追加字体图标：将压缩包内的selection.json文件导入官网重新选择



## 3.CSS三角形写法

```css
 .box2 {

​            width: 0;

​            height: 0;

​            /* 此处是为了兼容低版本 */

​            line-height: 0;

​            font-size: 0;

​            /* 是四边变透明 */

​            border: 100px solid transparent;

​            /* 选出其中需要的一面 */

​            border-left: 100px solid green;

​        }




```

## 4.CSS用户界面样式

### 4.1更改用户鼠标样式

```html


  <ul>
        <li style="cursor: default;">我是小白，默认样式</li>
        <li style="cursor: pointer;">我是鼠标小手样式</listyle>
        <li style="cursor: move;">我是鼠标移动样式</li>
        <li style="cursor:text;">我是鼠标文本样式</li>
        <li style="cursor: not-allowed;">我是鼠标静止样式</li>
    </ul>


```

### 4.2取消表单轮廓线和文本域防脱拽

```css


<style>
        /* 取消表单轮廓线 */
        input {
            outline: none;
        }

​        /* 文本域防脱拽（文本与最好分一行写） */
​        textarea {
​            resize: none;
​            outline: none;
​        }
​    </style>
```



## 5.Vertical-align属性

### 5.1作用对象

行内和行内块有效

```css
<style>
    /* 图片和文字垂直居中 */
    img{
        vertical-align: middle;
    }
</style>
```



### 5.2图片底测有空白缝隙

图片底测有一个空白缝隙，是因为图片和文字基线对齐，解决方法有两种

1.给图片添加vertical-align: bottom;/middle/top等属性

2.把图片转化为块级元素

```css
.box .content1 li img {

  width: 228px;

  height: 154px;

  /* 此处解决图片底测有空白缝隙 */

  /* display: block; */

  vertical-align: bottom;

}


```

## 6.溢出文字省略号显示

单行文字溢出省略号显示

```css
 div{

​            width: 150px;

​            height: 60px;

​            background-color: pink;

​            /* normal文字显示不开自动换行 */

​            /* white-space: normal; */

​             /*1.nowrap文字显示不开强制一行显示*/

​            white-space: nowrap;

​            /* 2.溢出的部分隐藏 */

​            overflow: hidden;

​            /* 3.将溢出的文字显示为省略号 */

​            text-overflow: ellipsis;

​        }
```



## 7.布局技巧

### 7.1margin负值：

1.让盒子margin左侧偏移1px，可以压住相邻盒子的边框

2.鼠标经过过某个盒子的时候，提高当前盒子的层级即可（如果无定位，可以添加相对定位；如果有定位，可以添加z-index）

```css


  <style>
        li {
            position: relative;
            float: left;
            /* 利用margin负值解决边框重叠 */
            margin-left: -1px;
            list-style: none;
            width: 150px;
            height: 200px;
            border: 1px solid #000;
        }

​        /* ul li:hover {
​            如何盒子无定位，鼠标经过添加相对定位
​            position: relative;
​            border: 1px solid red;
​        } */
​        ul li:hover {
​            /* 如何盒子有定位，鼠标经过通过调节层级z-index来解决 */
​             border: 1px solid red;
​             z-index: 1;
​        }
​    </style>
```



### 7.2文字围绕附浮动元素的妙用

<!DOCTYPE html>
<html lang="en">

  <!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box {
            width: 900px;
            height: 400px;
            background-color: pink;
        }

        /* 只用浮动图片就行 */
        .picture {
            float: left;
            width: 630px;
            height: 378px;
        }

        .picture img {
            width: 100%;
        }
    </style>
</head>

<body>
    <div class="box">
        <div class="picture">
            <img src="./img/特斯拉.jpeg" alt="">
        </div>

        <p>7月22日，台湾知名艺人林志颖在驾驶一辆特斯拉Model X ( 参数 | 询价 | 图片 ) 时发生严重交通事故，车辆撞上路肩隔离岛，车上乘客林志颖受伤送医，林志颖儿子受到惊吓，两人暂无生命危险。</p>
    </div>
</body>

</html>




### 7.3CSS三角强化

```css
 <style>
        /* .box{
            width: 0;
            height: 0;
            border-top: 100px solid transparent;
            border-right: 50px solid red;
            border-bottom: 0 solid green;
            border-left: 0 solid pink;
        } */
        .box{
            width: 0;
            height: 0;
            /* 1.只保留右边框有颜色 */
            border-color:transparent red transparent transparent;
            /* 2.所有样式都为solid */
            border-style: solid;
            /* 3.上边框宽度要大 右边框宽度要小 其他未0 */
            border-width: 100px 50px 0 0;
        }
    </style>
```



### 7.4css初始化（重设浏览器样式）

原因：因为浏览器的兼容问题，不同浏览器对有些标签的默认值是不同的，如果没对CSS初始化往往会出现浏览器之间的页面显示差异。

每次新开发网站或新网页时候通过初始化CSS样式的属性，为我们将用到的CSS或html标签更加方便准确，使得我们开发网页内容时更加方便简洁，同时减少CSS代码量，节约网页下载时间。



好处：提高编码质量

```css
/* 清除所有标签的内外边距 */
* {
  margin: 0;
  padding: 0;
}

/* em和i的字体不倾斜 */
em,
i {
  font-style: normal;
}

/* 清除li的小圆点 */
li {
  list-style: none;
}

img {
  /* border 0是为了兼容低版本浏览器，如果图片外面包含了链接会有边框问题 */
  border: 0;
  /* 取消图片底测有空白缝隙 */
  vertical-align: middle;
}

button {
  /* 鼠标经过buttons时变成小手 */
  cursor: pointer;
}

a {
  /* 改变链接颜色 */
  color: #666;
  /* 清楚链接下划线 */
  text-decoration: none;
}

a:hover {
  color: #c81623;
}

button,
input {
  /* 都是宋体： "\5B8B\4F53", sans-serif;  \5B8B\4F53 Unicode写法 */
  font-family: Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB,
    "\5B8B\4F53", sans-serif;
}
body {
  /* 抗锯齿形，解决文字放大不会有锯齿 */
  -webkit-font-smoothing: antialiased;
  background-color: #fff;
  font: 12px/1.5 Microsoft YaHei, Heiti SC, tahoma, arial, Hiragino Sans GB,
    "\5B8B\4F53", sans-serif;
  color: #666;
}

/* 把元素隐藏 */
.hide,
.none {
  display: none;
}

/* 清除浮动 */
.clearfix:after {
  visibility: hidden;
  clear: both;
  display: block;
  content: ".";
  height: 0;
}
.clearfix {
  *zoom: 1;
}

```



# 二.疑惑的地方

## 1.CSS三角强化

```css
 <style>
        /* .box{
            width: 0;
            height: 0;
            border-top: 100px solid transparent;
            border-right: 50px solid red;
            border-bottom: 0 solid green;
            border-left: 0 solid pink;
        } */
        .box{
            width: 0;
            height: 0;
            /* 1.只保留右边框有颜色 */
            border-color:transparent red transparent transparent;
            /* 2.所有样式都为solid */
            border-style: solid;
            /* 3.上边框宽度要大 右边框宽度要小 其他未0 */
            border-width: 100px 50px 0 0;
        }
    </style>
```

疑惑之处在于width: 0;height: 0;这两个属性是否需要写，因为不写一样可以达到效果，css讲究代码简洁