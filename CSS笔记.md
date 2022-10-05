# CSS

## CSS基础知识

### 背景

- HTML代码中，样式代码和内容代码放在一起很杂乱，不宜阅读。无法实现更好的效果。

- HTML和css之间的关系

  - HTML只负责页面的内容

  - css负责美化页面。代码还是写在HTML页面里面。

### 概念

- 层叠样式表（cascading style sheet）

  - 层叠：css的一个特性。
  - 样式：指标签的外观部分。比如尺寸，颜色，形状，字体等。
  - 表：css的代码书写的表现形式类似于一张表。

- 作用：书写css代码用于美化页面。


### 三种使用方式

1. 嵌入方式：利用每个标签自带的``style``属性来设置样式。（用的少）
2. 内联方式：在``<head></head>``中添加``<style></style>``来写css代码。
3. 外联方式：创建一个以``.css``为后缀的文件，在文件中书写css代码，在HTML页面中的``<head></head>``中通过``<link href="css文件路径">``引入css文件。

```html
1.<img scr="" style="css代码">
2.	<head>
    	<style></style>
	</head>
3.<link href="css文件路径" />
```



### CSS代码书写格式

- css代码由选择器和属性代码构成。

  ```css
  css选择器{
      css属性名1:属性值1;
      css属性名1:属性值2;
  }
  ```

- css会通过标签选择器来找到需要设置样式的标签。设置对应的样式（css属性名）。

- css注释：/* 注释内容 */

# CSS基础属性

## 文字类

- ``color``：设置标签的文本颜色。对标签以及其子标签都有效果。支持的值：字面量、十六进制、RGB。
  - RGB: 红色（R）/绿色（G）/蓝色（B）,他们的取值是 0~255，他们三个的组合可以得到非常丰富的颜色。
    - 两个特殊：0,0,0 表示黑色 255,255,255 表示白色

  - 十六进制：#rrggbb
    - 两个特殊：#000000 表示黑色 #ffffff 表示白色
    - 注意：红绿蓝三个颜色是成对出现的，那么可以简写，比如： #ffffff->#fff         #000000->#000 #ff00ff->#f0f       #00ff99->#0f9

- ``font-size``：设置字体大小。默认字体和浏览器有有关，一般为微软雅黑16px。对标签以及其子标签都有效果。
- ``font-weight``：设置标签文字的粗细程度。可以取数字100-900，也可以使用bold粗体，bolder更粗。
  - 默认值：normal，等同于400。
  - 其他值：bold/thin。

- ``font-family``：设置标签文字的字体类型。默认字体跟系统有关。
- ``font-style``：字体风格，控制斜体。
  - italic/oblique：斜体
- ``text-decoration``:设置文本的样式。默认超链接有下划线。
  - none： 删除样式。（删除a标签的下划线）
  - underline：下划线。超链接会默认有这个。
  - line-through：删除线。
- ``text-align``：文本对齐。left、center、right。可以用于tr，td。
  - justify：文字向两侧对齐，对最后一行无效。
- ``line-height``：设置标签一行内容的高度，简称行高。标签里的一行内容会显示在行高得中间。可以用px。

  - 文字垂直居中：设置行高为和标签的高度一直。
- ``@font-face``：自定义字体

  - 计算机中每种字体就有自己的字体模板文件，一般后缀名是``.ttf``，``.fon``类的文件。


```css
/*引入字体并设置名字*/
@font-face{
    font-family:"字体的名字"
    src:url("字体文件的路径")
}
/* 让浏览器从操作系统（电脑）中去寻找这些字体，如果找到了，就不继续寻找了，如果没有找到，就依次往后面去找，把最终的字体用来渲染页面的内容 */
font-family: 'Courier New', Courier, monospace;
```


## 尺寸类

- ``width``：设置标签的宽度，以**px**或**百分比**为单位。
- ``height``：设置标签的高度，以像素或百分比为单位。
- ``border``：设置标签的边框。需要设置边框的宽度，边框的样式，边框的颜色。
  - ``border:1px solid red``：一个像素的红色实心边框。``dashed``为虚线。none为取消边框。
  - border-left、border-right、border-top、border-bottom。单独设置四条边框。
  - border-radius：圆角。如果只提供一个值，相当于把这个值应用到四个角上。如果提供四个值，则按照左上，右上，右下，左下的顺序设置圆角。
  - border透明色：transparent
- ``object-fit``：图片适配尺寸处理
  - ``object-position``：设置图片的显示位置


```css
/* 让当前容器跟浏览器通高同宽 */
width: 100vw;
height: 100vh;

```

## 背景

- ``background-color``：设置背景颜色
  - transparent：设置颜色为透明。

- ``background-image``：设置某个标签的背景图片
  - url("图片路径")

- ``background-repeat``：设置背景图片是否重复。默认是重复（repeat）。
  - no-repeat：不要重复。以此用极小的图片实现整个的背景图。

- ``background-size``：背景图片大小
  - contain：适应当前容器
  - cover：设置背景图片拉伸

- ``background-position``：设置背景图片的显示位置。写为x轴px和y轴px。也可以选center。

## 列表

- ``list-style-type``：设置每个列表项的图表样式。默认是circle,既小圆点。如果为none，则没有图标样式。是给ul设置的。
- ``list-style-image``：设置列表项的图标为指定的图片。给ul设置。
- ``list-style-position``：设置列表项图标的位置，内部inside或外部outside，不能设置具体的xy坐标。
- **``list-style``**：一个快捷的组合属性，可以同时设置``list-style-type``，``list-style-image``，``list-style-position``。
- 去掉``padding``：ul有默认的16px的margin，以及40px的左padding。

```css
list-style-type:none
list-style-image:url("图片地址");
list-style-position:inside;
list-style:url("图片地址") inside lower-roman;
list-style:none   /*←直接啥也没有*/
```

## 其他

- ``margin:0 auto;``：特殊用法。用于将某个标签相对页面水平居中。不适用于标签的内容。可以用于table。
  - 是针对块级元素的，如果是行内元素用text-align。
- ``outline``：用来描述一个元素的轮廓。轮廓不会改变盒子模型。
  - none：取消浏览器默认边框，针对表单元素。
  - 轮廓和边框有什么区别？
    - 边框会属于盒子模型（box）的一部分，设置了边框的元素，会增加整个元素的宽高。
    - 轮廓不会改变盒子模型。
- ``display``：设置HTML标签的显示模式。在非必要情况下，不推荐进行display转换。
  - block：将元素转换为块级元素。独占一行，可以设置宽高和内外边距。
    - p，h1~h6，table，tr，ul，ol，dl，li，hr
  - inline：将元素转换为行内元素。同行显示，默认不能设置宽高。
    - a，span
  - inline-block：将元素转换为行内块级元素。同时具备两者的特点，可以设置宽高内外边距，同时又是横向排列。
    - td，input，text area，select，button，img
  - none：隐藏元素，会将元素从页面中移除，不再占用文档空间。
  - 注意：
    - 几何属性（width/height）对行内元素是无效的，因为行内元素的宽高是根据它的内容来决定的。一定要给行内元素设置宽高，那么就需要将行内元素转换成块级元素。
    - 把元素转换成inline-block并不是实现元素横向排列的最优选择，有专门的布局方式（flex）可以让块级元素实现横向排列。而不是通过 display : inline-block;
    - 转换的意义是什么？应不应该使用？
      - 转换的意义是应对一些无法很好处理的特殊情况，否则应该始终坚持使用行内元素/块级元素默认的显示模式。
      - 在非必要情况下，不推荐进行display转换，原因：
        1. 代码的可读性。
        2. 浏览器的重回回流机制。浏览器性能损失。
- ``cursor``：设置鼠标样式。
  - pointer：变成小手，用的最多。a标签默认是此属性。
  - progress/wait：windows的话是沙漏，mac是转盘，代表处理当中。
  - none：鼠标隐藏。做游戏可以用。
- ``opacity``：设置标签的透明度，范围为0~1。0为完全透明，1为完全不透明。
- ``overflow``：控制溢出区域。
  - hidden：表示完全隐藏溢出内容。
  - scroll：表示使用滚动条显示溢出内容。



# CSS技巧

### 图文混排

- 如何让两个行内元素对齐：

  - ``vertical-align``：用于设置行内元素的垂直对齐方式。middle是居中。
  - ``vertical-align:middle;``：给图片设置，使图片跟文字居中对齐。
  - 如果还有空隙的话可能是换行导致的。
  - 把input的浏览器默认padding改掉。button的height默认包含了padding和border。
- ``line-height``和``vertical-align``之间的区别：

  - ``line-height``：用于设置标签内部一行内容的垂直对齐。设置为标签的高度可以实现内部一行内容垂直居中。

  - ``vertical-align``：用于设置行内元素之间的垂直对齐方式。设置为middle可以实现行内元素之间居中对齐。（一般是参考图片和表单元素，图片和文字根据中间的一条线对齐。）
- 图文混排的技巧——父标签里的行内元素垂直居中：给父标签设置``line-height:父标签高度;``、给里面的所有子标签设置``vertical-align:middle;``。
  - 原因：默认按照div左上角对齐。给div设置line-height之后可以让图片和文字相对于div来说居中对齐（父标签和子标签对齐），但是二者参考的位置不一样所以二者之间并不和谐。所以需要再给图片设置vertical-align保证子标签和子标签也对齐。

### 行内元素换行空格问题

- 如果行内块级元素代码之间换行，那么页面两个标签中会有一个空格
- 解决：给父标签设置font-size为0；如果子标签有文字，就单独给子标签设置font-size。

### transform实现水平垂直居中

- 使用 ``top:50%;``和``left:50%;`` 让小矩形处于以左上角为原点的中心位置。
- 再使用 ``transform:translate(-50%,-50%);`` 让小矩形往左上移动自身长宽的50%。 

### 元素隐藏的区别

* ``display:none;``和``visibility:hidden;   ``的区别：
- display的话是直接隐藏，不渲染标签，拿不到标签的属性。
  - 从文档中移除，用户看不见它，以前占用的空间也会被释放。

- visibility是渲染到页面上 ，只是看不到，检查的话是可以看到的，但是占位置很少用。
  - hidden时隐藏，visible时显示。只是让用户看不见，原来占用的空间依然会被占用。※要么显示要么不显示，没有中间值所以不能过渡。

- opacity：0。不透明度调成0，让用户看不见，原来占用的空间依然会被占用。设置时0~1调整。

### 一些小技巧

- class=“x y”，代表有多个类名，css中选x可以选中，选y也可以。



# CSS基础选择器

## 标签选择器

```css
body{
	background-color:black;
    color:white;
}
效果：对页面所有的body标签内容设置背景颜色为黑色。字体颜色为白色。
```

- 会对页面上所有同类型的标签设置通用样式


## id选择器

- 能够对**单独的**某个标签设置样式。
- 步骤
  - 给需要单独设置样式的标签添加``id``属性
  - 利用css的id选择器来设置样式

```css
html中要写的:
<td id="logo"></td>
css中调用:
#logo{
    text-align:left;
}
效果：会对id属性为logo的标签设置其内容左对齐。
```

- 同一个页面不允许有一样的id属性。


## class选择器

- 对具有**相同class属性**的**多个标签**同时设置样式。
- 步骤
  - 给需要设置样式的这些标签设置一样的class属性。class属性是每个标签都可以设置的。
  - 利用class选择器来进行设置
  - 特别适合页面上多个标签有同样的样式

```css
.demo{
    color:white;
}
效果：对class属性为demo的所有标签设置文字颜色为白色。	
```

## 伪类选择器

- 根据用户鼠标的行为来改变标签的样式。

- 分类：

  - :link：超链接专属，页面一打开超链接就用的样式。（旧属性基本不用）
  - :visited：超链接专属，超链接被访问之后的样式。（旧属性偶尔会用到）
  - ``:hover``：鼠标经过时，悬停到标签上时标签使用的样式。
  - ``:active``：鼠标点击标签不释放时使用的样式。
  - ``:focus``：当标签获取鼠标焦点时使用的样式。比如点击输入框。

- 使用语法

  ```css
  非伪类选择器:hover{
      css属性名1:属性值1;
      color:pink;   /*鼠标触碰的时候文字变粉色*/
  }
  input:focus{
      border:1px solid blue;   /*鼠标点击后输入框变色*/
      outline:none
  }
  ```


## 组合选择器

- 概念：同时使用id，class，标签选择器中的一种或多种，来达到给多个标签设置样式的目的。
- 作用：减少不必要的class代码
- 思路：利用标签的嵌套关系来精确寻找需要设置样式的标签。



- ``后代选择器``：

  - 选择器1 选择器2 选择器3{}：选择所有的1下面的——所有的2下面的——所有的3。 

  ```css
  找到所有table标签里的a标签，字体颜色为白色。
  table a{
      color:while;
  }
  找到所有body标签下的class为item的标签，字体颜色为红色
  body .item{
      color:red;
  }
  ```



- ``标签/类/id组合选择器``：所选择的结果同时包含它们要求的每一个条件。

  ```css
  同时具备 c1 c2 c3 类的元素。
  .c1.c2.c3{} 
  
  id为c1，并且class列表中具有c2和c3的元素。
  #c1.c2.c3{}
  
  class列表中具有c1，并且id等于c2，并且在div里。
  div.c1#c2{}
  ```

- ``直接元素选择器``：选择直接子元素。

  ```css
  选择器1>2{}
  
  注意：孙子元素和后代元素不能被选择。写法不能加空格。
  ```

  

- ``:nth-of-type``：取当前元素的兄弟元素的第n个。

  ```css
  选择第三个兄弟元素（必须是div），可以隔断(比如中间有其他标签)：
  div:nth-of-type(3){}
  ```

  

- ``:nth-child``：取当前元素的第n个节点的当前元素。括号里可以放数字和公式。

  ```css
  选择第2个div，不能隔断：
  div:nth-child(2){}
  
  选择所有的偶数/奇数索引：
  div:nth-child(even/odd){}
  
  每隔三个选一个：
  div:nth-child(3n+1){}
  
  例子：如何选择同一个class下的第一个div?
  .class:nth-child(1)
  ```

  

- ``:not``：取非

  ```css
  选择除了第一个li之外的所有li：
  li:not(:first-child){}
  
  :last-child 最后一个
  ```

  



## 选择器命名规范

- id属性，class属性

  - 尽量能体现标签的作用
  - 不能以数字开头

  ```html
  <a id="head_logo"></a>
  ```

  

# CSS特性

## CSS权重

- 概念
  - 不同的选择器匹配到同一个标签，并且对同一个css属性设置时，因为涉及到css属性的最终归属问题，css就提供了一套权重机制，来处理这样的情况。根据权重的大小来决定css属性最终的归属。
  - 越详细的选择器权重越高： ``!important``关键字 > 行内样式 > id > class > 其他
  - 权重问题一般只在面试的过程中问到，实际工作中遇到的比较少。以后项目开发中一般都会less/scss/sacc来编写css。
  
- 权重的计算方式

  - 加法

    - 原理：给每一种基础的css选择器（id，class，标签，伪类）设置为不同的数值。权重的数值就等于使用的选择器的权值之和。

    - 权值计算：

      - id：100
      - class：10
      - 标签，伪类：1

      ```css
      body .list li{
          权值为1+10+1=12
      }
      #list li{
          权值为100+1=101  所以会使用第二个处理
      }
      ```

      

  - 4个0

    - 原理：是依次比较基础选择器的数量多少来决定权重的大小。
    - （行内样式，id选择器，class选择器，标签选择器）
      - 从左往右开始对比，有一个比值不相等，就结束，大的权重更高；除非相等才比较下一个选择器的权值。

## CSS继承

- css中，指部分的css属性可以由父标签传递给子标签。

- 自动继承的css属性

  - 以font开头的css属性系列。
  - text-align，line-height，color，cursor，list-style，opacity（透明度）等。

- 其他有inherit取值的css属性（手动继承）：css属性名:inherit;

  

- 继承的作用

  - 减少css代码：对于一些通用的样式，比如字体类型，大小，颜色等完全可以给body设置，特殊的再单独设置。

- 应用场景

  - 给父标签或者body标签设置通用的样式，子标签直接继承使用，无需格外的代码。



# CSS布局

## <div\>

### 概念

- 本身是一个HTML4的标签。因为div的特殊性而一直被作为css布局的核心标签。

### 特点

- 本身默认样式极少，除了是一个块级元素。
- 本身没有太多的默认属性。
- 默认宽度为100%。

### 总结

- 本身不具有太多的默认的样式或属性，对css来说可塑性极强。可以实现任何想要的效果。比如布局的一部分，或者模块之类。

## 盒模型

### 概念

- css会把所有的标签都当成一个个“盒子”，通过css所提供的相关css属性能够实现任意标签的尺寸设置以及位置定位。而由这些css属性构成的体系就是所谓的盒模型。

### 尺寸

- ``width``：设置盒子的内容宽度。
- ``height``：设置盒子的内容高度。
- ``border``：设置盒子的边框。

### 边距

- ``padding``：设置内边距。内边距是指内容和边框之间的距离。默认是和width是分开的。设置padding之后盒子会被撑大。

  - padding会被计算在盒子的尺寸中。
  - input默认padding。button的height默认包含了padding和border。

  ```css
  语法：与margin一致。
  padding四个值：上 右 下 左。
  padding两个值：上下 左右
  padding一个值：上下左右。四条边内边距统一设置
  padding-left/right/top/bottom:20px; 设置左/右/上/下内边距
  ```

- ``margin``：设置外边距。即盒子和另一个挨着的盒子之间的距离。

  - 用于设置盒子（标签）之间的距离。由此可以设置盒子的位置，达到页面布局的目的。

  ```css
  margin:20px; 设置四条边的外边距
  margin-left/right/top/bottom:20px; 设置左/右/上/下外边距
  margin: 0 auto; 含义：上下外边距为零，左右外边距自动。所以产生居中的效果。
  ```

### 盒模型的宽高计算

- 盒子的总宽度：
  - ``width``+``padding（水平）``+``border（水平）``+``margin（水平）``
  - 后三个别忘了两边都有，计算两边的值。
- 盒子的总高度：
  - ``height``+``padding（垂直）``+``border（垂直）``+``margin（垂直）``

### 总结

- 标准盒模型padding和border是不算在width，height中的。是格外的。

## IE盒模型（怪异盒模型）

- 概念：

  - 和标准盒模型一样，使用5个css属性来设置盒子的尺寸以及位置。

- 区别：

  - IE盒模型中，用户设置的宽度和高度的计算方式和标准盒模型是不同的。

  ```css
  标准盒模型：
  width:内容宽度+padding+border
  height：内容高度+padding+border
  IE盒盒模型：
  盒子总宽度：width+margin
  盒子总高度：height+margin
  ```

### box-sizing

- 可以对该标签实现标准盒模型和ie盒模型的切换。

- 在现在浏览器中，大多数标签都是默认用的标准盒模型。可以用box-sizing css属性来切换。

  ```css
  box-sizing:content-box; 标准盒模型（默认）
  box-sizing:border-box;  IE盒模型
  ```




## div+css布局

- 以css盒模型为核心，以div来设计和实现页面的一种布局技术。
- 思想：把页面的所有内容，都划分为不同的盒子中，借助css盒模型完成页面的布局。



## 浮动

- ``float:left/right/none``：
  - 使用了float进行浮动的元素，会脱离文档流（父元素相当于无法感知它有这个子元素了）。因此，浮动起来的元素不会占用以前空间，那些没有浮动的元素就会趁虚而入，占用腾出来的空间。
  - 注意：如果一个父元素中的所有子元素都浮动了，代表所有的子元素都不再占用空间。因此，我们需要给父元素设置一个高度，否则会有高度塌陷的问题。



# 伪元素、定位

- ``:before/:after``：伪元素。（标准的是两个冒号）
- 什么叫做伪元素？
  - 我们没有在html中定义的元素，可以通过css动态地往元素地开头位置和结束位置追加一个元素，这个元素叫伪元素。

- 如何写：

  - 选择器::before 或 选择器::after{}

    - 必须有display:””根据实际情况赋值

    - 必须有content:””需要展示到伪元素中的内容，里面可以有文字。一般是给一个空。

- 注意：
  - 如果display为块级元素，那么需要给伪元素设置宽高，否则看不到。
  - 如果display为行内元素，那么需要给伪元素的content属性赋上内容（文字），因为行内元素的宽高是根据它的内容决定的。



## 定位

- 作用：打破正常文档流（行内元素横向排列，块级元素独占一行），让元素可以被放在页面的任意位置。

- 分类：

- 给``position``设置不同的值来实现定位

  - static：正常文档流，默认值。

  - relative：相对定位，把自己原来的位置看作（0，0）点，然后相对于此进行定位。定位之后，原来的位置占用的空间依然占用。

  - absolute：绝对定位，相对于最近的已定位的父元素或者根元素进行定位。定位之后，原来的位置占用的空间被释放。

    ```css
    position:absolute;
    top:0;        y轴保持原来的位置不变
    left:100px;   x轴从离它最近的已被定位的元素或者根元素的位置，向右边移动100px
    ```

    

  - fixed：固定定位

    - 不管页面滚动与否，始终都显示在视口的指定的坐标的位置。

    - 并且它会从文档流中释放原来占用的空间。

      

- ``z-index``：层级顺序

  数字越大，越靠上。数字越小，越靠下。可以理解为图层。图层0~10这样。

- 定位和伪元素的结合

  - 比如给一个div设置很靠近的一体类样式，可以使用伪元素和子绝父相。
  - ``子绝父相``
    - 子元素设置绝对定位，给父元素设置相对定位。把子元素牢牢地靠着父元素。

# 弹性布局

## 基础

### 背景

* div+css布局的不便之处
  * 没有自适应、大量时间花在水平或垂直居中、清理浮动

### 概念

* 弹性布局是css第三代布局技术，具有自适应特点，用于替代div+css布局或起到辅助作用。完全替代很难。

### 作用

* 让弹性布局中的元素能够适应不同的容器宽度，比如浏览器宽度。
* 实现内容快速的居中

### 基本语法

* 原理：
  * 给容器标签设置``display:flex | inline-flex``都可以将该容器变为弹性容器。通过设置弹性布局提供的css属性，能够对弹性容器的**直接子标签**进行布局的控制。直接子标签也称为弹性子项目。
* ``display:flex``和``inline-flex``都是将该标签作为弹性容器，区别在于弹性容器的兄弟标签。
  * 如果是flex，那么对其他兄弟标签来说，弹性容器是一个普通的块级元素。
  * 如果是inline-flex，那么对其他兄弟标签来说，弹性容器是一个普通的行内块级元素。
* ※一般不会对弹性容器设置高度，因为自适应。

### 主轴和侧轴

### 弹性布局相关css

* ``flex-direction``：设置弹性容器的主轴。对弹性容器设置
  * row：默认，即水平。→
  * row-reserve：相反的水平方向。←
  * column：垂直方向。↓
  * column-reserve：相反的垂直方向。↑
* ``flex-wrap``：对弹性容器设置，是否允许子标签换行。
  * nowrap：默认，不换行
  * wrap：换行
* ``justify-content``：设置弹性子项目在主轴上的对齐方式。对弹性容器设置。
  * center：水平居中。
  * flex-start：从主轴开头进行排列。
  * flex-end：从主轴末尾进行排列。
  * space-between：弹性子项目均等平分主轴空间，贴住边框。
  * space-around：弹性子项目两边不贴边框，空出来半个缝隙。
  * space-evenly：弹性子项目的所有空隙均分主轴空间。
* ``align-content``：设置弹性子项目在侧轴上的对齐方式。对弹性容器设置。
  * 属性和justify完全一样。
  * ※必须设置flex-wrap。保证弹性子项目可以换行。
  * stretch：如果设置为此，弹性子项目的默认高度就是弹性容器的高度。
* ``align-items``：设置弹性子项目之间的对齐方式。保留原有子项目大小。
  * stretch：当弹性子项目高度为auto或没设高度时，会自动拉伸高度。高度会刚好容下内容
  * baseline | flex-end 往交叉轴下靠 | flex-start 往交叉轴上靠 | center 交叉轴中心分布
* ``flex-grow``：弹性因子。左右布局时，占用的比例。
  * 比如父元素div中有两个子元素div。
  * 一个CSS属性设置1，一个设置2。前者占父元素三分之一的宽度，后者占三分之二。




# 动画相关

## 过渡动画：

从一个状态到另一个状态之间的变化（只有开始和结束状态）

- ``transition：all 1s linear;``

  拆分：

  - transition-property:width, background-color; 动画属性，哪些属性发生变化时需要执行过度动画。all代表所有属性。可以改成单个的属性比如width。
  - transition-duration:3s; 动画的时间
  - transition-timing-function:linear; 动画运动时间函数（决定运动速度快慢）。
    - linear：匀速
    - ease：中间快，两头慢
    - ease-in：开始慢，之后快
    - ease-out：开始快，结束时候减慢
    - ease-in-out：（开始和结束都慢）两头慢

  其他：

  - transition-delay:1s; 动画延时

2D转换：

- ``transform``：不会影响到布局。也就是说不管怎么转换它都不会影响到其他的元素的位置，并且之前占用的空间依然占用。

  - ratate(45deg)：顺时针旋转（45度）。
  - scale(2)：缩放比例，取值应该 >=0，小于1时会缩小，大于1时会放大。
    - scaleX(2)只放大宽；scaleY(2)只放大高。
  - translate：
    - translateY(100px)垂直方向移动，正值向右，负值向左
    - translateX(100px)水平方向移动，正值向下，负值向上

- ``transform-origin``：

  转换的圆点，常用的值是center，可选的值是left/right/top/bottom的四种组合（表示四个顶点）

## 关键帧动画：

从一个状态到另一个状态的之间的变化（可以更精细化地控制开始和结束之间的很多状态）

- ``animation: 定义的名字 3s linear infinite;``

- 拆分：

  - animation-name:rotate; 动画名称

  - animation-duration:2s; 动画时长

  - animation-timing-function:linear;  动画的运动规律

  - animation-iteration-count:infinite; 动画的执行次数（无限）

  - animation-delay:5s; 动画的执行延时

- @keyframes 定义的名字{}

## animation-fill-mode（动画填充模式）

- 定义动画播放时间之外的状态。顾名思义，就是在动画播放完了之后给它一个状态。

- animation-fill-mode : none | forwards | backwards |both;
  - （1）none，播放完之后不改变默认行为，默认值
  - （2）forwards则是停在动画最后的的那个画面
  - （3）backwards则是回调到动画最开始出现的画面
  - （4）both则应用为动画结束或开始的状态
- 案例：例如动态写字特效，需要在动画执行完毕后，将动画暂停到最后一帧。



```css
div {
    background: red;
    width: 100px;
    height: 100px;
    margin: 100px auto;
    transform: rotate(45deg);
}
@keyframes dlxt-rotate {
    /* 1、顺时针旋转1周 */
    25% {
        transform: rotate(360deg);
    }
    /* 2、逆时针旋转一周 */
    50% {
        transform: rotate(0deg);
    }
    /* 3、顺时针旋转一周 */
    75% {
        transform: rotate(360deg);
    }
}
/* 希望鼠标移进去的时候，顺时针旋转1周，再逆时针旋转一周，
再顺时针旋转一周 */
div:hover {
    animation: dlxt-rotate 10s linear;
}
```

## 小技巧

- 动画中用scaleY代替height，去掉抖动。

