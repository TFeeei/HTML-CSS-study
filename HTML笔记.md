# HTML标签

## 头部代码

- ``<!doctype html>``：页面声明。告诉浏览器该页面以HTML5版本来解析。必须是第一句代码。

- ``<html></html>``页面的根标签，包含了页面的所有其他标签，表示一个页面标签。

  - lang：指代的HTML文件使用语言。en表示英文。zh表示中文。

- ``<head></head>``：页面的头部，一般用于配置信息以及设置页面标题。

  - ``<meta>``：用于配置页面的相关信息，比如说用什么浏览器内核打开，用什么编码集来解析文字。
  - ``<title></title>``：指定页面的标题

- ``<body></body>``：页面的主体，所有的页面展示内容都写在这里面。

- 注释：

  ```html
  <!-- html注释内容 -->
  vscode可以利用crtl+/来对当前光标处快速生成或者删除注释。
  ```



## 基础标签

- ##### a标签：负责超链接  

  ~~~html
  <a href="跳转的页面地址">文本内容</a> 	
  ~~~

  - ``href``属性指定当用户点击文本时要跳转到哪个页面
  - 标签中的属性指的是标签中的一个特征
  - ``target="_blank"``加上此属性的时候创建新页面再跳转



- ##### img标签：负责图片

  ~~~html
  <img src="图片地址" width="200"/>
  ~~~

  - ``src``属性：负责要展示的图片地址
  - ``width``：设置图片的宽度；``height``：设置图片的高度。建议宽高只设置其中一个，另一个会按照图片比例自动调整。

  

- ##### 标题标签\<h1>到\<h6>

  ~~~html
  <h1>h1文本内容</h1>
  <h2>h2文本内容</h2>
  <h3>h3文本内容</h3>
  <h4>h4文本内容</h4>
  <h5>h5文本内容</h5>
  <h6>h6文本内容</h6>
  ~~~

  - 数字越大，字体反而越小

    

- ##### p标签：段落标签

  ~~~html
  <p>
      段落内容
  </p>
  ~~~

  - 每个p标签都是独占一行

  - 不带首行缩进

    

- ##### br：换行标签

  ~~~html
  <br>
  ~~~

  - 一个``br``换一行。两个br换两行。

    

- ##### 特殊符号-空格：\&nbsp;

  ~~~html
  &nbsp;
  ~~~

  - 一个``&nbsp;``表示一个空格。



## 媒体标签

- audio：音频标签，用于播放音乐

- video：视频标签，用于播放视频

  - scr：表示媒体资源的地址

  - controls：表示显示控制按钮（播放，停止等）

  ```html
  <!-- src音频地址 -->
  <audio controls="controls" src="https://www.w3school.com.cn/i/horse.ogg"></audio>
  
  <video controls="controls" src=""></video>
  <!-- 小技巧：href属性中不知道要写什么的时候，加#号。 -->
  
  ```

  

- iframe：网页框架，把另一个网页的内容嵌入到当前的页面中，相当于小型浏览器。（html5中已经不再推荐使用iframe标签）

  - scr：需要嵌入的目标地址

  - frameborder

  ```html
  <!-- src地址就是需要嵌入的目标地址 -->
  <iframe width="100%" height="800px" src="https://baidu.com" frameborder="0"></iframe>
  ```

  

## 语义化标签（セマンティック要素）

- 语义化的好处：
  - 对SEO（搜索引擎优化）友好，使用良好的html语义化标签编写的网页在搜索引擎的结果中更容易靠前展示。
  - 对开发人员友好，因为语义化实际上就是对标签的作用给了非常恰当的说明，这样开发人员读到你的代码时不需要完全理解也能够明白大概在做什么。

- 推荐使用的语义化标签（替代div）：
  1. header：头部区域。
  2. nav：导航，常用于导航。比如首页的菜单，友情链接等。
  3. main：主内容区域。
  4. article：文章区域。
  5. footer：尾部区域。
  6. section：节点。
  7. aside：一般用于表示侧边栏。



# HTML表格

## 基础标签

- ``<table></table>``：表示一个表格，表格里的行和列需要使用``tr``和``td``来表示。

  - ``border``：指的表格的边框。默认是0，以数字为单位。
  - ``width``：设置整个表格的宽度，以数字为单位。
  - ``height``：设置整个表格的高度，以数字为单位。
  - ``align``：设置整个表格相对于页面的水平对齐方式。

  ~~~html
  <table border="1" width="300" height="200" align="center">
      <tr>
          <td>第一行第一列</td>
          <td></td>
          <td></td>
      </tr>
      <tr>
          <td>第二行第一列</td>
          <td></td>
          <td></td>
      </tr>
  </table>
  ~~~

  

- ``<tr></tr>``：一个`tr`表示表格中的一行，自身不包含单元格，单元格需要`td`来表示。

  - ``align``：设置一行内容的对齐方式，可以用``left``，``right``，``center``。默认是left。

    ```html
    <th align="center"></th>
    ```

    

- ``<td></td>``：一个``td``表示一个单元格，``td``需写在``tr``里面。

  - ``width``:设置某个单元格的宽度，以数字为单位。
  - ``herght``:设置某个单元格的高度，以数字为单位。
  - 同样支持``align``。

- ``<th></th>``：表示表格标题行中的一个单元格。

  - ``td``和``th``的区别：``th``里文字会自动加粗。

    

- 快捷写法：

  - 在VScode中输入<u>td*数量</u>→直接创建出相当数量的td语法。
  - <u>table#id名>tr>td*数量</u>→直接创建出带有id名的表格以及内容
  - (tr>td乘4)乘数量→创建出相当数量的带有4个td的tr




## 表格扩展

- 合并单元格

  - ``colspan``：针对同一行的单元格的合并。跨列合并。是td,th专属属性。

    ```html
    <td colspan="3"></td>
    ```

  - ``rowspan``：针对同一列不同行的单元格的合并。跨行合并。是td,th专用属性。

    ```html
    <td rowspan="3"></td> 第一个单元格
    ```

- 控制单元格的间距(后期会被css替代)

  - ``cellspacing``：table标签专属，用于控制单元格之间的距离，以数字为单位。

    ```html
    <table cellspacing="2" cellpadding="">
        
    </table>
    ```

    

  - ``cellpadding``：table标签专属。单元格内容和单元格边框之间的距离。以数字为单位



- 路径

  - 绝对路径：http://开头或者c:/以盘符开头的路径


  - 相对路径：从参考的位置出发，另一个文件所在的位置就是相对路径。参考位置的不同，即便是同一个相对路径，得到的最终文件是不一样的。

    ```html
    <img src="images/icon5.png" />
    ```




## 列表

- 分类

  - 无序列表（小圆点）

    - ``ul``：定义一个无序列表
    - ``li``：一个li指的是列表的一个列表项。一个列表可以有多个列表项。

    ```html
    <ul>
        <li>第一个列表项</li>
        	<ul>二级目录
                <li>二级目录第一个列表项</li>
        	</ul>
        <li>第二个列表项</li>
        <li>第三个列表项</li>
    </ul>
    ```

    

  - 有序列表（数字）

    - ``ol``：定义一个有序列表
    - ``li``：列表项

  - 定义列表<dl>（用的很少）

    - 用<dl>定义一个定义列表。
    - 每个列表项由一个标题<dt>和正文<dd>来表示



## 表单

- form

  - 一个``<form></form>``表示一个表单，form标签里面可以嵌入表单元素，形成一个页面上的表单。
  - 作用：配置用户表单提交的路径以及方式
  - 标签属性：
    - ``method``：指定提交的方式，默认是get，还可以取post等。
    - ``action``：指定表单数据提交的路径。手动指定，一般指定的是我们服务器的ip地址。也可以指定为另一个页面用于查看效果。

  ```html
  <form action="index.html">
      用户名：<input type="text" > <br>
      密码：<input type="password" >
      性别<input type="radio" name="sex">男 <input type"radio" name="sex">女
  	爱好<input type="checkbox">唱 <input type="checkbox">跳 <input type="checkbox">rap 
      <button>登录</button>
  </form>
  当点击表单里的按钮时，会把数据提交到index.html
  ```

  

表单元素：

- ``input``：实现各种框。会根据自身的type属性来确定具体表现的是什么框。

  - ``type``：
    - 输入框：``type="text"``。input标签type属性的默认值
      - 如果需要带有默认值，可以指定``value``属性，比如默认admin等。
      - 如果需要显示默认值，可以指定``placeholder``属性，比如默认用户名/邮箱等。
    - 密码框：``type="password"``。
    - 单选框：``type="radio"``。
      - 如果需要多个单选框只选其中一个，需所有单选框有一样的``name``属性。
      - 可以给默认选项添加``checked``属性设置默认选项。
    - 多选框：``type="checkbox"``
      - 想把checkbox的选框和文字对齐时，指定``vertical-align: middle;``。
    - 按钮（html5 有单独标签实现）：``type="button"``
      - 给input设置``value``属性来给按钮添加文本。type为button只是一个样式。没有提交功能。
      - 如果type为``submit``，可以进行表单提交。
      - 如果type为``reset``，可以进行表单重置。
  - 多个input可以同行显示。

  ```html
  <input type="text" value="admin">
  <input type="password" >
  <input type="radio" name="sex" checked >男 <input type"radio" name="sex">女
  <input type="checkbox">唱 <input type="checkbox">跳 <input type="checkbox">rap 
  <input type="button" value="登录">
  <input type="submit" value="提交"> 
  <input type="reset" value="重置">
  ```

  

- ``select``：实现下拉菜单，需搭配``option``标签

  - 下拉菜单

  ```html
  <select>
      <option>请选择学历</option>
      <option>选项1</option>
      <option value="" selected>选项2</option>
      <option>选项3</option>
  </select>
  ```

  - 每个``option``就是一个选项。
  - 给option添加``selected``属性为设置默认选项。

- ``textarea``：实现文本域

  ```html
  <textarea cols="" rows="" value="" ></textarea>  
  ```

  - ``cols``：一行的列数，间接的用于设置宽度。
  - ``rows``：有多少行，间接的用于设置高度。
  - ``value``：可以设置文本域的默认内容。

- ``button``：实现按钮（html5）

  - 处于form标签里的button按钮会自带提交功能。

  ```html
  <button>登录</button>
  ```

  

## 表单补充（html5）

1. 针对input的类型进行了扩展

   1. 邮箱：``type="email"``。电子邮箱的认证。
   2. 颜色：``type="color"``
   3. 日期：``type="date"``；``type="month"``
   4. 范围：``type="range"``。单独使用没什么意义。需要配合JavaScript。
   5. 数字：``type="number"``只允许input输入数字。
   6. ``type="file" accept=".png,.jpg,.jpeg,.gif"``上传文件。只允许xx格式。

   ```html
   年龄：<input type="date">
   喜欢的颜色：<input type="color">
   出生日期：<input type="date">
   邮箱：<input type="email"> ←提交的时候会提示你缺少@符号。
   ```

   

2. 提供``required``属性，设置某个表单元素为必填。

3. 提供``disabled``属性，设置某个表单元素为不可修改。

```html
<input type="password" required>
<input type="submit" value="提交" disabled> ←不能提交了
```







# 小技巧



##### 插入谷歌地图：

1. 查找该地址
2. 共有
3. 地図を埋め込む
4. 复制HTML
