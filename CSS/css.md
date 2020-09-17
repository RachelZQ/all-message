1:掌握盒子水平垂直居中的五大方案
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        html,body{
            height: 100%;
            overflow: hidden;
        }
        .box{
            box-sizing: border-box;
            width: 100px;
            height: 50px;
            line-height: 48px;
            text-align: center;
            font-size: 16px;
            border: 1px solid lightblue;
            background: lightblue;   
        }
        /*定位1  需要考虑父级宽高且需计算*/
        body{
            position: relative;
        }
        .box{
            position: absolute;
            top:50%;
            left:50%;
            margin-left: -50px;
            margin-top: -25px;
        }
        /*定位2 不需要考虑父级宽高 但得有宽高
        body{
            position: relative;
        }
        .box{
            position: absolute;
            top: 0;
            bottom: 0;
            left: 0;
            right: 0;
            margin: auto;
        }
        */
        /*定位3 CSS3中使用transform不需要计算 也不需要父级宽高
            但兼容性不是很好
        body{
            position: relative;
        }
        .box{
            position: absolute;
            top:50%;
            left:50%;
            transform: translate(-50%,-50%);
        }*/


        /*display:flex   主轴和交叉轴都居中（即x和y轴） 但也需要考虑兼容性*/
        /*移动端常用做法*/
        /*body{
            display: flex;
            justify-content: center; 
            align-items: center;
        }*/

        /*通过javaScript来实现（使用需将下面body中js代码取消注释）*/
        /*body{
            position: relative;
        }*/

        /*使用display:table-cell 这种方法本身是用来控制文本的
        而且要求父级必须有固定宽高 百分比不算固定值 使用比较少（了解即可）
        */
        /*
        body{
            display: table-cell;
            vertical-align: middle;
            text-align: center;
            width: 500px;
            height: 500px;
        }
        .box{
            display: inline-block;
            
        }*/
        


    </style>
</head>
<body>
    <div class="box" id="box">
        居中显示
    </div>
    <!--通过javaScript来实现-->
    <script>
        /*let HTML=document.documentElement,
            winW=HTML.clientWidth,
            winH=HTML.clientHeight,
            boxW=box.offsetWidth,
            boxH=box.offsetHeight;
        box.style.position="absolute";
        box.style.left=(winW-boxW)/2+'px';
        box.style.top=(winH-boxH)/2+'px';*/
    </script>
</body>
</html>
```

2:标准盒模型、怪异盒模型（IE盒模型）和flex弹性伸缩盒模型以及多列布局
- 标准盒模型（box-sizing content-box）

content =content
<img src="https://img-blog.csdnimg.cn/20200222185449952.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjQyOTcxOA==,size_16,color_FFFFFF,t_70"></img>
- IE盒模型（box-sizing border-box）

content = width+padding+border

<img src="https://img-blog.csdnimg.cn/20200222185613912.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjQyOTcxOA==,size_16,color_FFFFFF,t_70"></img>
- 通过css中的box-sizing属性
 - 标准盒模型 ：content-box
 - IE盒模型 ： border-box

标准盒子模型，即box-sizing content-box，我们所写的width和height并不是最终盒子的宽高，而是content的，
盒子的宽高由我们的content+padding+border来组成的，但是这样在做项目时可能会遇到小问题，假如我想构建一个100x100的盒子大小，但是我发现我写的是width和height是100，于是我需要加上padding及border，但是加上去之后，盒子也会相应变大，这就造成改动麻烦。

后面css3中提供了IE盒子模型，能够直接控制盒子的大小。于是项目中大多数用上了IE盒子模型，以及我看过bootstrap以及bootelement-ui源码中大部分也是用的IE盒子模型

><div>以上回答方式，请读者可以好好体会一下，挖掘其中的亮点！</div>

- FLEX盒模型（弹性布局）
布局的传统解决方案基于盒子模型，依赖于display属性、position属性、float属性，特殊布局不方便，2009年,W3C提出--FLEX布局
--- 
任何一个容器都可以指定为Flex布局,(Webkit 内核的浏览器，必须加上-webkit前缀)
```javascript
.box{
    display: -webkit-flex; /* Safari */
    display:flex;
}
```
行内元素
```javascript
.box{
    display: inline-flex;
}
```
<font color=red>注意：</font>设为 Flex 布局以后，子元素的float、clear和vertical-align属性将失效。
