# HTML和CSS

MDN是Mozilla Developer Network的缩写，是Mozilla开发者社区，一个完整的学习平台，你可以在这里深入学习Web技术以及能够驱动Web的软件。

HTML：超文本标记语言（HTML，HyperText Markup Language）用于描述、定义网页内容。

CSS：层叠样式表（CSS，Cascading Style Sheets）用于描述网页内容的外观与展示。

HTTP:超文本传输协议（HTTP，Hypertext Transfer Protocol）用于传输网页中的 HTML 及其他超媒体文档。

JavaScript: 是在浏览器中运行的编程语言。它可以为你的网站或应用程序添加交互性和其他动态功能。

随着 [Node.js](https://developer.mozilla.org/en-US/docs/Glossary/Node.js) 的出现，你也可以在服务器上运行 JavaScript。

Web Components 是一套不同的技术，允许您创建可重用的定制元素（它们的功能封装在您的代码之外）并且在您的 Web 应用中使用它们。

## 1. HTML基础

**基本标签**

```html
<h1>标题</h1>
<p>段落</p>
<a href="链接地址">这是一个链接</a>
 <!--使用 Target 属性，你可以定义被链接的文档在何处显示。-->

<img src="图片地址"/>
 <!--替换文本属性（Alt）,当图片无法加载的时候以文本替换-->

<br/>  <!--定义换行-->
<hr /> <!--标签在 HTML 页面中创建水平线。-->

<div>
    定义文档中的节或区域（块级）。
</div>
<span>定义文档中的行内的小块或区域。</span>
```

**html元素**

HTML 元素指的是从开始标签（start tag）到结束标签（end tag）的所有代码。

**html属性**

属性总是以名称/值对的形式出现，比如：*name="value"*。

**html文本格式化标签**

```html
<strong>This text is strong</strong>
<big>This text is big</big>
<em>This text is emphasized</em>
<i>This text is italic</i>
<small>This text is small</small>
<sub>subscript</sub>
<sup>superscript</sup>

```

**html表格**

表格由 <table> 标签来定义。每个表格均有若干行（由 <tr> 标签定义），每行被分割为若干单元格（由 <td> 标签定义）。字母 td 指表格数据（table data），即数据单元格的内容。数据单元格可以包含文本、图片、列表、段落、表单、水平线、表格等等。

属性：

- border边框
- th表头，大多数浏览器会把表头显示为粗体居中的文本。
- 跨行：rowspan=“”
- 跨列：colspan=“”
- 单元格边距cell padding
- 单元格间距cell spacing
- align对齐方式

**html列表**

1. 无序列表

   无序列表是一个项目的列表，此列项目使用粗体圆点（典型的小黑圆圈，支持自定义，指定type=（默认disc实心圆，circle空心圆，quare实心正方型））进行标记。

   无序列表始于 <ul> 标签。每个列表项始于 <li>。

2. 有序列表

   列表项目使用数字进行标记。（同理type=（1,a,i,I））

   有序列表始于 <ol> 标签。每个列表项始于 <li> 标签。

3. 自定义列表

   自定义列表以 <dl> 标签开始。每个自定义列表项以 <dt> 开始。每个自定义列表项的定义以 <dd> 开始。

   ```html
   <dl>
   <dt>Coffee</dt>
   <dd>Black hot drink</dd>
   <dt>Milk</dt>
   <dd>White cold drink</dd>
   </dl>
   ```

**html块**

大多数 HTML 元素被定义为块级元素或内联元素。块级元素在浏览器显示时，通常会以新行来开始（和结束）。典型的为<h1>, <p>, <ul>, <table>

内联元素在显示时通常不会以新行开始。典型的是<b>, <td>, <a>, <img>

**div元素**

该元素是块级元素，定义文档中的分区或节，是组合其他元素的容器

**html的类**

对 HTML 进行分类（设置类），使我们能够为元素的类定义 CSS 样式。

**html布局**

1. 使用div元素布局，通过设置css进行定位

2. 使用h5的语义元素

   HTML5 提供的新语义元素定义了网页的不同部分：

   | header  | 定义文档或节的页眉             |
   | ------- | ------------------------------ |
   | nav     | 定义导航链接的容器             |
   | section | 定义文档中的节                 |
   | article | 定义独立的自包含文章           |
   | aside   | 定义内容之外的内容（比如侧栏） |
   | footer  | 定义文档或节的页脚             |
   | details | 定义额外的细节                 |
   | summary | 定义 details 元素的标题        |

3. 使用table布局，用的少

**响应式布局**

- RWD 指的是响应式 Web 设计（Responsive Web Design）
- RWD 能够以可变尺寸传递网页
- RWD 对于平板和移动设备是必需的

最好的办法是使用css框架：

例如使用 Bootstrap

> Bootstrap 是最流行的开发响应式 web 的 HTML, CSS, 和 JS 框架。
>
> Bootstrap 帮助您开发在任何尺寸都外观出众的站点：显示器、笔记本电脑、平板电脑或手机。
>
> 缺点是：不使用定制的时候，缺乏新意，导致大同小异

**html框架**

在同一个浏览器窗口显示不止一个页面(注意不能和body标签一起使用)

```html
<!--第一列被设置为占据浏览器窗口的 25%。第二列被设置为占据浏览器窗口的 75%。-->
<frameset cols="25%,75%">
   <frame src="frame_a.htm">
   <frame src="frame_b.htm">
</frameset>

<!--用于在网页中显示网页-->
<iframe src="URL" frameborder="0" height width></iframe>
```

**html头部元素**

- 文档的标题

  title 标题定义文档的标题。

- 所有链接一个目标（为页面上的所有链接规定默认地址或默认目标）

  如何使用 base 标签使页面中的所有标签在新窗口中打开。

- 文档描述

  使用 <meta> 元素来描述文档。元数据不会显示在页面上，但是对于机器是可读的。用于规定页面的描述、关键词、文档的作者、最后修改时间以及其他元数据。name和content的属性

- 文档关键词

  使用 <meta> 元素来定义文档的关键词。元数据可用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他 web 服务。

- 重定向用户

  如何把用户重定向到新的网址。

- link定义文档与外部资源之间的关系。

  常用于连接样式表

- 还有style和script

**html预留字符**

例如小于号&lt和不间断空格&加nbsp

**html文档类型**

现在常用的是html5(2012)

```
<!DOCTYPE html>
```

2013年 XHTML5  x代表扩展的意思（可扩展超文本标记语言）它是更严格更纯净的 HTML 版本

## 2. ***HTML表单

html表单用于收集不同类型的用户输入，使用form标签定义html表单

**表单元素**

- [ ] input元素

  它有很多形态，通过设置不同的type属性，注意：**`起始标签为必须，而关闭标签是禁止的。**` 

  text 定义常规文本输入。且默认文本字段的长度为20个字符

  submit 提交按钮，提交表单

  password 定义密码字段

  > ## 输入限制
  >
  > 这里列出了一些常用的输入限制（其中一些是 HTML5 中新增的）：
  >
  > | 属性      | 描述                               |
  > | --------- | ---------------------------------- |
  > | disabled  | 规定输入字段应该被禁用。           |
  > | max       | 规定输入字段的最大值。             |
  > | maxlength | 规定输入字段的最大字符数。         |
  > | min       | 规定输入字段的最小值。             |
  > | pattern   | 规定通过其检查输入值的正则表达式。 |
  > | readonly  | 规定输入字段为只读（无法修改）。   |
  > | required  | 规定输入字段是必需的（必需填写）。 |
  > | size      | 规定输入字段的宽度（以字符计）。   |
  > | step      | 规定输入字段的合法数字间隔。       |
  > | value     | 规定输入字段的默认值。             |
  >
  > multiple 属性是布尔属性。如果设置，则规定允许用户在 <input> 元素中输入一个以上的值。
  >
  > multiple 属性适用于以下输入类型：email 和 file。
  >
  > placeholder属性设置拥有占位符文本的输入字段：

  radio 定义单选按钮输入（选择多个选择之一）

  ```html
  <form>
  <input type="radio" name="sex" value="male" checked />Male
  <br>
  <input type="radio" name="sex" value="female" />Female
  </form> 
  ```

  checkbox复选框

  button设置成按钮

  date应该包含日期的输入字段

- [ ] select元素定义下拉列表，列表选项为option，可以使用selected设置预选项

- [ ] textarea设置文本域（多行输入字段）

- [ ] button定义可点击的按钮（跟上面的区别？）

  > 总结：<button>具有<input type="button" ... >相同的作用但是在可操控性方面更加强大。
  >
  > 具体的说：
  >
  > 1. input是单标签，而button是闭合标签
  > 2. button的值更灵活（文字、图像、移动、水平线、框架、分组框、音频视频），且可以设置css样式
  > 3. 鼠标单击事件、弹出信息的代码可直接写在<button>标签中，

**表单属性**

- action属性定义在提交表单时执行的动作。如果省略 action 属性，则 action 会被设置为当前页面。
- method属性规定在提交表单时所用的 HTTP 方法（*GET* 或 *POST*）
- 如果要正确地被提交，每个输入字段必须设置一个 name 属性。

## 3.HTML5

HTML5 是最新的HTML标准，它提供的新元素和新的 API 简化了 web 应用程序的搭建。

HTML5 是跨平台的，被设计为在不同类型的硬件（PC、平板、手机、电视机等等）之上运行。

HTML5 中默认的字符编码是 UTF-8。

**新特性**

HTML5 的一些最有趣的新特性：

- 新的语义元素

  | <article>    | 定义文档内的文章。                                   |
  | ------------ | ---------------------------------------------------- |
  | <aside>      | 定义页面内容之外的内容。                             |
  | <bdi>        | 定义与其他文本不同的文本方向。                       |
  | <details>    | 定义用户可查看或隐藏的额外细节。                     |
  | <dialog>     | 定义对话框或窗口。                                   |
  | <figcaption> | 定义 <figure> 元素的标题。                           |
  | <figure>     | 定义自包含内容，比如图示、图表、照片、代码清单等等。 |
  | <footer>     | 定义文档或节的页脚。                                 |
  | <header>     | 定义文档或节的页眉。                                 |
  | <main>       | 定义文档的主内容。                                   |
  | <mark>       | 定义重要或强调的内容。                               |
  | <menuitem>   | 定义用户能够从弹出菜单调用的命令/菜单项目。          |
  | <meter>      | 定义已知范围（尺度）内的标量测量。                   |
  | <nav>        | 定义文档内的导航链接。                               |
  | <progress>   | 定义任务进度。                                       |
  | <rp>         | 定义在不支持 ruby 注释的浏览器中显示什么。           |
  | <rt>         | 定义关于字符的解释/发音（用于东亚字体）。            |
  | <ruby>       | 定义 ruby 注释（用于东亚字体）。                     |
  | <section>    | 定义文档中的节。                                     |
  | <summary>    | 定义 <details> 元素的可见标题。                      |
  | <time>       | 定义日期/时间。                                      |
  | <wbr>        | 定义可能的折行（line-break）。                       |

  ![HTML5 语义元素](https://www.w3school.com.cn/i/ct_sem_elements.png)

- 新的表单控件，比如数字、日期、时间、日历和滑块。

- 强大的图像支持（借由 <canvas> 和 <svg>）

- 强大的多媒体支持（借由 <video> 和 <audio>）

- 强大的新 API，比如用本地存储取代 cookie。

你甚至可以定义新元素

使用脚本document.createElement("新元素名")，并设置display属性为block，这样就定义的一个新的块级元素。

### **3.1 HTML5图像**

#### 3.1.1 canvas 

定义使用js的图像，画布是一个矩形区域，您可以控制其每一像素。

```html
<!--向HTML5页面添加canvas元素-->
<canvas id="myCanvas" width="200" height="100"></canvas>

<!--canvas 元素本身是没有绘图能力的。所有的绘制工作必须在 JavaScript 内部完成-->
<script type="text/javascript">   //注意是使用id来寻找canvas元素
var c=document.getElementById("myCanvas");
var cxt=c.getContext("2d"); //创建context对象
cxt.fillStyle="#FF0000"; //规定了样式
cxt.fillRect(0,0,150,75); //fillRect 方法规定了形状、位置和尺寸。
//在左上角（0，0）开始，绘制一个150x75的矩形
</script>
```

还可以绘制线条，

圆

绘制渐变背景

把一张图片放在画布上

```html
<script type="text/javascript">

var c=document.getElementById("myCanvas");
var cxt=c.getContext("2d");
var img=new Image()
img.src="flower.png"
cxt.drawImage(img,0,0);

</script>
```

#### 3.1.2 SVG

可缩放矢量图形(Scalable Vector Graphics)。  定义使用SVG的图像绘制

- SVG 用于定义用于网络的基于矢量的图形
- SVG 使用 XML 格式定义图形
- SVG 图像在放大或改变尺寸的情况下其图形质量不会有损失

与其他图像格式相比（比如 JPEG 和 GIF），使用 SVG 的优势在于：

- SVG 图像可通过文本编辑器来创建和修改
- SVG 图像可被搜索、索引、脚本化或压缩
- SVG 是可伸缩的
- SVG 图像可在任何的分辨率下被高质量地打印
- SVG 可在图像质量不下降的情况下被放大

虽然canvas和SVG都允许在浏览器上创建图形，但是他们在本质上是不一样的：

- SVG 是一种使用 XML 描述 2D 图形的语言。

  SVG 基于 XML，这意味着 SVG DOM 中的每个元素都是可用的。您可以为某个元素附加 JavaScript 事件处理器。

  在 SVG 中，每个被绘制的图形均被视为对象。如果 SVG 对象的属性发生变化，那么浏览器能够自动重现图形。

- Canvas 通过 JavaScript 来绘制 2D 图形。

  Canvas 是逐像素进行渲染的。

  在 canvas 中，一旦图形被绘制完成，它就不会继续得到浏览器的关注。如果其位置发生变化，那么整个场景也需要重新绘制，包括任何或许已被图形覆盖的对象。

**HTML5新的媒介元素**

| 标签     | 描述                                 |
| -------- | ------------------------------------ |
| <audio>  | 定义声音或音乐内容。                 |
| <embed>  | 定义外部应用程序的容器（比如插件）。 |
| <source> | 定义 <video> 和 <audio> 的来源。     |
| <track>  | 定义 <video> 和 <audio> 的轨道。     |
| <video>  | 定义视频或影片内容。                 |

### 3.2 HTML5 API

#### 3.2.1 HTML5 Geolocation（地理定位）

用于定位用户的位置。

#### 3.2.2 在HTML5中拖放

在HTML5中拖放（Drag 和 Drop）是很常见的特性，任何元素都可以拖放的。

#### 3.2.3 HTML本地存储（local storage）

通过本地存储（Local Storage），web 应用程序能够在用户浏览器中对数据进行本地的存储。

在 HTML5 之前，应用程序数据只能存储在 cookie 中，包括每个服务器请求。本地存储则更安全，并且可在不影响网站性能的前提下将大量数据存储于本地。

与 cookie 不同，存储限制要大得多（至少5MB），并且信息不会被传输到服务器。

本地存储经由起源地（origin）（经由域和协议）。所有页面，从起源地，能够存储和访问相同的数据。

HTML 本地存储提供了两个在客户端存储数据的对象：

- window.localStorage - 存储没有截止日期的数据

  ```javascript
  // 存储（名称/值对）
  localStorage.setItem("lastname", "Gates");
  // 取回
  document.getElementById("result").innerHTML = localStorage.getItem("lastname");
  //删除
  localStorage.removeItem("lastname");
  ```

- window.sessionStorage - 针对一个 session 来存储数据（当关闭浏览器标签页时数据会丢失）

  常用方法同上。

#### 3.2.4 HTML5应用程序缓存

使用应用程序缓存，通过创建 cache manifest 文件，可轻松创建 web 应用的离线版本。

#### 3.2.5 HTML Web Workers

Web worker 是运行在后台的 JavaScript，不会影响页面的性能。？？？

#### 3.2.6 HTML5 Server-Sent

Server-Sent 事件允许网页从服务器获得更新。

## 4. css基础

css指层叠样式表cascading style sheet，定义如何显示一个HTML元素，多重样式将层叠为一个，他们的优先级为：

1. 浏览器缺省设置
2. 外部样式表
3. 内部样式表（位于 <head> 标签内部）
4. 内联样式（在 HTML 元素内部）（最高）

**css的创建方式：**

1. 外部样式表：适用于样式需要应用在多个页面的情况

   ```html
   <head>
   <link rel="stylesheet" type="text/css" href="mystyle.css" />
   </head>
   ```

2. 内部样式表：使用于单个文件

   ```html
   <head>
   <style type="text/css">
     hr {color: sienna;}
     p {margin-left: 20px;}
     body {background-image: url("images/back40.gif");}
   </style>
   </head>
   ```

3. 内立案样式表：当样式只需要在元素上作用一次的时候

**多重样式表的继承：如果某些属性在不同的样式表中被同样的选择器定义，那么属性值将从更具体的样式表中被继承过来。**

### 4.1 css语法

css规则由两个部分组成：选择器，以及一条或多条声明。

选择器分为id选择器和class类选择器以及元素名选择器，通配选择器（*),该选择器可以与任何元素匹配。	

声明由{属性：值，属性：值}组成，属性的继承：子元素默认从父元素继承，如果你不希望继承，单独设置即可，但是要注意低版本得浏览器得兼容性问题。

### 4.2 ***css选择器

#### 4.2.1 css类选择器

类选择器允许独立于文档元素的方式来制定样式。使用.来使用类选择器。由于类名可以重名，所以允许结合元素选择器来使用

```css
//只希望只有段落的important显示为红色
p.important {color:red;}
```

css多类选择器： 例如class 为 important 的所有元素都是粗体，而 class 为 warning 的所有元素为斜体，class 中同时包含 important 和 warning 的所有元素还有一个银色的背景 。

```html
//无论顺序，只要包含即可
<p class="important warning">
This paragraph is a very important warning.
</p>
<p class="important">
This paragraph is a very important.
</p>
<p class="warning">
This paragraph is a warning.
</p>
```

```css
.important {font-weight:bold;}
.warning {font-style:italic;}
.important.warning {background:silver;}
```

​	

#### 4.2.2 ID选择器

某些方面id选择器和类选择器类似，但是它使用#选择元素，并且id唯一，且ID 属性不允许有以空格分隔的词列表（所以不可以结合使用）。

#### 4.2.3 属性选择器

属性选择器可以根据元素的属性及属性值来选择元素。

```css
//如果您希望把包含标题（title）的所有元素变为红色，可以写作：
*[title] {color:red;}

//多个属性选择，
a[href][title] {color:red;}
```

未完待续

#### 4.2.4 派生选择器

派生选择器允许你根据文档的上下文关系来确定某个标签的样式。

**后代选择器**（两个元素之间的层次间隔可以是无限的。）：

```css
//例如对li标签下所有的strong标签设置属性
li strong {
    font-style: italic;
    font-weight: normal;
  }
```

**子元素选择器**

```css
//如果您希望选择只作为 h1 元素子元素的 strong 元素，可以这样写：
h1 > strong {color:red;}
```

**相邻兄弟选择器**

可选择紧接在另一元素后的元素，且二者有相同父元素。

#### 4.2.5 伪类

伪类的语法：

```css

```

典型的伪类就是a:link，CSS 类也可与伪类搭配使用。

```css
a:link {color: #FF0000}		/* 未访问的链接 */
a:visited {color: #00FF00}	/* 已访问的链接 */
a:hover {color: #FF00FF}	/* 鼠标移动到链接上 */
a:active {color: #0000FF}	/* 选定的链接 */
```

- 在 CSS 定义中，a:hover 必须被置于 a:link 和 a:visited 之后，才是有效的。
- 在 CSS 定义中，a:active 必须被置于 a:hover 之后，才是有效的。
- 伪类名称对大小写不敏感。

 还可以使用:first-child 伪类来选择元素的第一个子元素

类似的还有伪元素：

| 属性                                                         | 描述                             | CSS  |
| ------------------------------------------------------------ | -------------------------------- | ---- |
| [:first-letter](https://www.w3school.com.cn/cssref/pr_pseudo_first-letter.asp) | 向文本的第一个字母添加特殊样式。 | 1    |
| [:first-line](https://www.w3school.com.cn/cssref/pr_pseudo_first-line.asp) | 向文本的首行添加特殊样式。       | 1    |
| [:before](https://www.w3school.com.cn/cssref/pr_pseudo_before.asp) | 在元素之前添加内容。             | 2    |
| [:after](https://www.w3school.com.cn/cssref/pr_pseudo_after.asp) | 在元素之后添加内容。             | 2    |

### 4.3 css样式

#### **背景属性**

| 属性                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [background](https://www.w3school.com.cn/cssref/pr_background.asp) | 简写属性，作用是将背景属性设置在一个声明中。                 |
| [background-attachment](https://www.w3school.com.cn/cssref/pr_background-attachment.asp) | 背景图像是否固定（fixed）或者随着页面的其余部分滚动（默认scroll）。 |
| [background-color](https://www.w3school.com.cn/cssref/pr_background-color.asp) | 设置元素的背景颜色。                                         |
| [background-image](https://www.w3school.com.cn/cssref/pr_background-image.asp) | 把图像设置为背景。                                           |
| [background-position](https://www.w3school.com.cn/cssref/pr_background-position.asp) | 设置背景图像的起始位置。（5个关键字，百分比（左上角开始），长度值（左上角开始）） |
| [background-repeat](https://www.w3school.com.cn/cssref/pr_background-repeat.asp) | 设置背景图像是否及如何重复。no-repeat                        |

#### 文本属性

| 属性                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [color](https://www.w3school.com.cn/cssref/pr_text_color.asp) | 设置文本颜色                                                 |
| [direction](https://www.w3school.com.cn/cssref/pr_text_direction.asp) | 设置文本方向。                                               |
| [line-height](https://www.w3school.com.cn/cssref/pr_dim_line-height.asp) | 设置行高。                                                   |
| [letter-spacing](https://www.w3school.com.cn/cssref/pr_text_letter-spacing.asp) | 设置字符间距。                                               |
| word-spacing                                                 | 设置字间距。-0.5em                                           |
| [text-align](https://www.w3school.com.cn/cssref/pr_text_text-align.asp) | 对齐元素中的文本。left、right （默认）和 center，justify（两端对齐） |
| [text-decoration](https://www.w3school.com.cn/cssref/pr_text_text-decoration.asp) | 向文本添加修饰。none，underline，overline，line-through，blink |
| [text-indent](https://www.w3school.com.cn/cssref/pr_text_text-indent.asp) | 缩进元素中文本的首行。5em，-5em，或者百分比（相对于父元素）  |
| text-shadow                                                  | 设置文本阴影。CSS2 包含该属性，但是 CSS2.1 没有保留该属性。  |
| [text-transform](https://www.w3school.com.cn/cssref/pr_text_text-transform.asp) | 控制元素中的字母。none，uppercase，lowercasse。capitalize    |
| unicode-bidi                                                 | 设置文本方向。                                               |
| [white-space](https://www.w3school.com.cn/cssref/pr_text_white-space.asp) | 设置元素中空白的处理方式。normal将会忽略所有空白和换行，pre则不会 |
|                                                              |                                                              |

#### 字体

#### css列表

| 属性                                                         | 描述                                                 |
| ------------------------------------------------------------ | ---------------------------------------------------- |
| [list-style](https://www.w3school.com.cn/cssref/pr_list-style.asp) | 简写属性。用于把所有用于列表的属性设置于一个声明中。 |
| [list-style-image](https://www.w3school.com.cn/cssref/pr_list-style-image.asp) | 将图象设置为列表项标志。                             |
| [list-style-position](https://www.w3school.com.cn/cssref/pr_list-style-position.asp) | 设置列表中列表项标志的位置。                         |
| [list-style-type](https://www.w3school.com.cn/cssref/pr_list-style-type.asp) | 设置列表项标志的类型。                               |

#### css表格

| 属性                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [border-collapse](https://www.w3school.com.cn/cssref/pr_tab_border-collapse.asp) | 设置是否把表格边框合并为单一的边框。collapse合并，separate分离 |
| [border-spacing](https://www.w3school.com.cn/cssref/pr_tab_border-spacing.asp) | 设置分隔单元格边框的距离。                                   |
| [caption-side](https://www.w3school.com.cn/cssref/pr_tab_caption-side.asp) | 设置表格标题的位置。top/botton                               |
| [empty-cells](https://www.w3school.com.cn/cssref/pr_tab_empty-cells.asp) | 设置是否显示表格中的空单元格。                               |
| [table-layout](https://www.w3school.com.cn/cssref/pr_tab_table-layout.asp) | 设置显示单元、行和列的算法。                                 |

#### css轮廓

outline：color/style(点dotted，虚线dashed，solid实线)/width

### 4.4 css框模型

![CSS 框模型](https://www.w3school.com.cn/i/ct_boxmodel.gif)

在 CSS 中，width 和 height 指的是内容区域的宽度和高度。增加内边距、边框和外边距不会影响内容区域的尺寸，但是会增加元素框的总尺寸。

通常浏览器对body有的会有默认的外边距，有的有外边距，因此我们需要对body的padding和margin都进行自定义

**padding**:top,rihgt,bottom,left; 有个值复制的规则：

> ```css
> p {margin: 0.5em 1em 0.5em 1em;}
> //css的值复制，允许我们不用输入重复的值
> p {margin: 0.5em 1em;}
> ```
>
> 如果为外边距指定了 3 个值，则第 4 个值（即左外边距）会从第 2 个值（右外边距）复制得到。如果给定了两个值，第 4 个值会从第 2 个值复制得到，第 3 个值（下外边距）会从第 1 个值（上外边距）复制得到。最后一个情况，如果只给定一个值，那么其他 3 个外边距都由这个值（上外边距）复制得到。

或者单独设置，可以为元素的内边距设置百分数值。百分数值是相对于其父元素的 **width** 计算的（不管是上下左右边距，都是相对父元素的宽度计算的），这一点与外边距一样。所以，如果父元素的 width 改变，它们也会改变。

**border**:宽度，样式，颜色；可以指定方向。注意，要设置边框宽度，必须设置样式，如果样式为none，那么边框根本就不存在，宽度自然为0；

style：dotted点状 solid实线 double双线 dashed虚线; 

颜色有一个默认值：transparent，有宽度，边框颜色为透明

**外边距的合并：**

1. 是指两个垂直边距相遇时，它们将形成一个外边距，且合并后的外边距的高度时二者之间的较大者。

2. 当一个元素包含在另一个元素中的时候（如果外面那个元素没有内边距或边框把外边距分隔开），它们的上和/或下外边距也会发生合并。

3. 假设有一个空元素，它有外边距，但是没有边框或填充。在这种情况下，上外边距与下外边距就碰到了一起，它们会发生合并。

   如果这个外边距遇到另一个元素的外边距，它还会发生合并。

注释：只有普通文档流中块框的垂直外边距才会发生外边距合并。行内框、浮动框或绝对定位之间的外边距不会合并。

### 4.5 ***css定位

positioning属性允许我们对元素进行定位。

定位的基本思想很简单，它允许你定义元素框相对于其正常位置应该出现的位置，或者相对于父元素、另一个元素甚至浏览器窗口本身的位置。

**一切皆为框**：例如块级元素即块框，行内元素即行内框，我们可以设置display属性来改变框类型，block块框，inline行内框，none没有框。

> 1.行内元素与块级元素（典型 的div）可以相互转换，通过修改display属性值来切换块级元素和行内元素，行内元素display：inline，块级元素display：block。
>
> 2.行内元素（典型的span）和其他行内元素都会在一条水平线上排列，都是在同一行的；块级元素却总是会在新的一行开始排列，各个块级元素独占一行，垂直向下排列，若想使其水平方向排序，可使用左右浮动（float：left/right）让其水平方向排列。
>
> 3.**行内元素不可以设置宽高，宽度高度随文本内容的变化而变化，但是可以设置行高（line-height）**，同时在设置外边距margin上下无效，左右有效，内填充padding上下无效，左右有效；块级元素可以设置宽高，并且宽度高度以及外边距，内填充都可随意控制。        
>
> 4.块级元素可以包含行内元素和块级元素，还可以容纳[内联元素](https://www.baidu.com/s?wd=%E5%86%85%E8%81%94%E5%85%83%E7%B4%A0&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao)和其他元素；**行内元素不能包含块级元素，只能容纳文本或者其他行内元素。**
>
> **行内块状元素**（inline-block）综合了行内元素和块状元素的特性，但是各有取舍。因此行内块状元素在日常的使用中，由于其特性，使用的次数也比较多。
>
> 　　行内块状元素特征：(1)不自动换行
>
> 　　　　　　　　　　　(2)能够识别宽高
>
> 　　　　　　　　　　　(3)默认排列方式为从左到右

如果把文本放在块级元素，例如div中，即使没有声明，它也会被当作段落对待（即块，**这种情况下称之为无名块框，不与专门定义的元素相关联，因此无法直接对无名块或行框应用样式，因为没有可以应用样式的地方**）

有三种定位机制：普通流（默认）、浮动float和绝对定位absolute。

普通流中的元素的位置由元素在 (X)HTML 中的位置决定。

块级框从上到下一个接一个地排列，框之间的垂直距离是由框的垂直外边距计算出来。

行内框在一行中水平布置。可以使用水平内边距、边框和外边距调整它们的间距。但是，垂直内边距、边框和外边距不影响行内框的高度。？？？由一行形成的水平框称为*行框（Line Box）*，行框的高度总是足以容纳它包含的所有行内框。不过，设置行高可以增加这个框的高度。

css的position属性：

- static

  元素框正常生成。块级元素生成一个矩形框，作为文档流的一部分，行内元素则会创建一个或多个行框，置于其父元素中。

- relative（相对定位）

  元素框偏移某个距离。元素仍保持其未定位前的形状，**它原本所占的空间仍保留。**怎么理解？看图

  ![1584508778258](C:\Users\11060\AppData\Roaming\Typora\typora-user-images\1584508778258.png)

- absolute（绝对定位）

  元素框从文档流**完全删除**，并相对于其包含块定位（移动到任意位置）。包含块可能是文档中的另一个元素或者是初始包含块。元素原先在正常文档流中所占的空间会关闭，就好像元素原来不存在一样（即普通流中其它元素的布局就像绝对定位的元素不存在一样（意思就是不影响咯））。元素定位后生成一个**块级框**，而不论原来它在正常流中生成何种类型的框。

- fixed

  元素框的表现类似于将 position 设置为 absolute，**不过其包含块是视窗本身，就是参考对象是浏览器。**

提示：相对定位实际上被看作普通流定位模型的一部分，因为元素的位置相对于它在普通流中的位置（自身原来的位置）。

> 当元素设置position:absolute、float:left、float:right中任意一个时，都会让元素以display:inline-block（行内框）的方式进行显示（特点是：可以设置长宽，默认宽度不占满父元素）。这时，再单独设置display:inline; display:block都是无效的。

处理元素溢出：overflow：hidden/scoll/默认visible溢出/auto浏览器自动处理了

Z-index：可被用于将在一个元素放置于另一元素之后，即元素堆叠方式。

vertical-align：设置元素垂直对齐方式

**css浮动**：浮动的框可以向左或向右移动，直到它的外边缘**碰到包含框或另一个浮动框的边框为止。**

如果包含框太窄，无法容纳水平排列的三个浮动元素，那么其它浮动块向下移动，直到有足够的空间。如果浮动元素的高度不同，那么当它们向下移动时可能被其它浮动元素“卡住”：

![CSS 浮动实例 2 - 向左浮动的元素 ](https://www.w3school.com.cn/i/ct_css_positioning_floating_left_example_2.gif)

由于浮动框不在文档的普通流中（即不再占据空间），所以文档的普通流中的块框表现得就像浮动框不存在一样。怎么理解？？？

浮动清理：使用clear。例如创建浮动框可以使文本围绕图像，如果我们不希望文字围绕图像，我们可以对文本使用clear。

> 联系页面布局中，我们对main区域的div进行浮动，对页脚设置clear。
>
> 这个做法的意义我还是没有搞清楚？
>
> 例如：div里面有文本和图片，且文字和图片设置了浮动，这时候因为浮动元素脱离了文档流，所以包围图片和文本的 div 不占据空间。
>
> 这个时候如何让包围元素在视觉上包围浮动元素呢？需要在这个元素中的某个地方应用 clear。例如在div中再添加一个空的div设置clear，还有一种做法就是对容器div也进行浮动，
>
> 不幸的是，下一个元素会受到这个浮动元素的影响。为了解决这个问题，有些人选择对布局中的所有东西进行浮动，然后使用适当的有意义的元素（常常是站点的页脚）对这些浮动进行清理。这有助于减少或消除不必要的标记。

**浮动的应用**：

1. 创建水平菜单：

   我们把 ul 元素和 a 元素浮向左浮动。li 元素显示为行内元素（元素前后没有换行）。这样就可以使列表排列成一行。ul 元素的宽度是 100%，列表中的每个超链接的宽度是 7em（当前字体尺寸的 7 倍）。

2. 创建首页布局

## 5. css高级

### 5.1 css水平对齐

对齐块元素：块元素指的是占据全部可用宽度的元素，并且在其前后都会换行。

1. 使用margin：auto;居中对齐，如果宽度是100%，则对齐没有效果。
2. 绝对定位position
3. 使用float属性来左右对齐

### 5.2 css尺寸

CSS 尺寸 (Dimension) 属性允许你控制元素的高度和宽度。同样，它允许你增加行间距。

| 属性                                                         | 描述                 |
| ------------------------------------------------------------ | -------------------- |
| [height](https://www.w3school.com.cn/cssref/pr_dim_height.asp) | 设置元素的高度。     |
| [line-height](https://www.w3school.com.cn/cssref/pr_dim_line-height.asp) | 设置行高。           |
| [max-height](https://www.w3school.com.cn/cssref/pr_dim_max-height.asp) | 设置元素的最大高度。 |
| [max-width](https://www.w3school.com.cn/cssref/pr_dim_max-width.asp) | 设置元素的最大宽度。 |
| [min-height](https://www.w3school.com.cn/cssref/pr_dim_min-height.asp) | 设置元素的最小高度。 |
| [min-width](https://www.w3school.com.cn/cssref/pr_dim_min-width.asp) | 设置元素的最小宽度。 |
| [width](https://www.w3school.com.cn/cssref/pr_dim_width.asp) | 设置元素的宽度。     |

### 5.3 css分类属性

CSS 分类属性允许你规定如何以及在何处显示元素。

| 属性                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [clear](https://www.w3school.com.cn/cssref/pr_class_clear.asp) | 设置一个元素的侧面是否允许其他的浮动元素。                   |
| [cursor](https://www.w3school.com.cn/cssref/pr_class_cursor.asp) | 规定当指向某元素之上时显示的指针类型。                       |
| [display](https://www.w3school.com.cn/cssref/pr_class_display.asp) | 设置是否及如何显示元素。none不会被显示，block块级元素，前后换行符；默认：inline内联元素，前后无换行；inline-block行内块元素； |
| [float](https://www.w3school.com.cn/cssref/pr_class_float.asp) | 定义元素在哪个方向浮动。                                     |
| [position](https://www.w3school.com.cn/cssref/pr_class_position.asp) | 把元素放置到一个静态的、相对的、绝对的、或固定的位置中。     |
| [visibility](https://www.w3school.com.cn/cssref/pr_class_visibility.asp) | 设置元素是否可见或不可见。                                   |

### 5.4 ***css导航栏

导航栏基本上是一个链接列表，由 <ul> 和 <li> 和<a>元素组成

垂直导航栏：

```html
//css
ul{
list-style-type:none;  //去掉默认的圆点框
margin:0;
padding:0;
}
a{
display:block;     // 把链接显示为块元素可使整个链接区域可点击（不仅仅是文本），同时也允许我们规定宽度。
width:60px;
text-decoration:none;    //去掉默认的下划线
}
//html	
<ul>
<li><a href="default.asp">Home</a></li>
<li><a href="news.asp">News</a></li>
<li><a href="contact.asp">Contact</a></li>
<li><a href="about.asp">About</a></li>
</ul>

```

水平导航栏：将li元素设置成displau：inline即可

### 5.5 css媒介类型

媒介类型(Media Types)允许你定义以何种媒介来提交文档。文档可以被显示在显示器、纸媒介或者听觉浏览器等等。

例如：@media 规则使你有能力在相同的样式表中，使用不同的样式规则来针对不同的媒介。

未完待续...

## 6. css3

CSS3 被划分为模块。其中最重要的 CSS3 模块包括：

- 选择器
- 框模型
- 背景和边框
- 文本效果
- 2D/3D 转换
- 动画
- 多列布局
- 用户界面

### 6.1 边框

通过 CSS3，您能够创建圆角边框，向矩形添加阴影，使用图片来绘制边框 - 并且不需使用设计软件。

- 圆角：border-radius：可设置四个属性值，值可以是长度,也可以是百分比，例如border-radius：6px；每个圆角的“水平半径”和“垂直半径”都设置为6px；

- 边框阴影：box-shadow

  外阴影（默认）：box-shadow: X轴  Y轴  Rpx  color;

  属性说明（顺序依次对应）： 阴影的X轴(向右，向左可以使用负值)    阴影的Y轴(向上可以使用负值)    阴影模糊值（大小）    阴影的颜色

  内阴影：box-shadow: X轴  Y轴  Rpx  color  inset;

   注意：此属性使用于盒模型 如(div,p,h1,h2,h3,h4,h5,h6等) 不是用来设置文字阴影   如果设置文字阴影请参考知识点:text-shadow（同理）

- border-image：用到再说。。。

**背景**：background-size/origin/clip

**文本效果**：text-shadow 类似box-shadow

**字体**：用到再说。。。

### 6.2 css3 转换（transform）

 通过转换transform，我们能够对元素进行移动、缩放、转动、拉长或拉伸。

####  6.2.1 2D 转换方法

- translate()：

  元素从其**当前位置**移动，根据给定的 left（x 坐标） 和 top（y 坐标） 位置参数：

- rotate():

  元素顺时针围绕一个定点（默认元素的中心，可以使用tranform-origin指定）旋转一定的角度。允许负值，元素将逆时针旋转。例如：transform：rotate(30deg）

- scale()：

  元素的尺寸会增加或减少，根据给定的宽度（X 轴）和高度（Y 轴）参数：

  例如：transform：scale(2,4) 把宽度转换为原始尺寸的 2 倍，把高度转换为原始高度的 4 倍。

- skew()：

  元素翻转给定的角度，根据给定的水平线（X 轴）和垂直线（Y 轴）参数。

  例如skew(30deg,20deg) 围绕 X 轴把元素翻转 30 度，围绕 Y 轴翻转 20 度。

- matrix()：所有 2D 转换方法组合在一起。需要六个参数

  ：旋转、缩放、移动以及倾斜元素。

####  6.2.2 3D 转换方法

- 旋转：

  > 浏览器支持：
  >
  > Internet Explorer 10 和 Firefox 支持 3D 转换。
  >
  > Chrome 和 Safari 需要前缀 -webkit-。
  >
  > Opera 仍然不支持 3D 转换（它只支持 [2D 转换](https://www.w3school.com.cn/css3/css3_2dtransform.asp)）。

  rotateX():元素围绕其 X 轴以给定的度数进行旋转。

  同理：过 rotateY(130deg) 方法，元素围绕其 Y 轴以给定的度数进行旋转130deg。

- 未完待续。。。

### 6.3 ***css3过渡（transition）

通过 CSS3，我们可以在不使用 Flash 动画或 JavaScript 的情况下，当元素从一种样式变换为另一种样式时为元素添加效果。

> 浏览器支持：
>
> Internet Explorer 10、Firefox、Chrome 以及 Opera 支持 transition 属性。
>
> Safari 需要前缀 -webkit-。

transition：属性 时间;  支持对多个属性添加效果

例如：transition: width 2s;作用于div的宽度，时长为2s；如果不指定时长，则没有过渡效果。

还可以指定transition-timing-function，规定过渡效果的速度曲线：

| 值                            | 描述                                                         |
| ----------------------------- | ------------------------------------------------------------ |
| linear                        | 规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）。 |
| ease                          | 默认值；规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）。 |
| ease-in                       | 规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)）。  |
| ease-out                      | 规定以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）。  |
| ease-in-out                   | 规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）。 |
| cubic-bezier(*n*,*n*,*n*,*n*) | 在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值。 |

transition-delay：2s；指定过渡效果2s后开始，默认是0

### 6.4 ***动画（animation）

使用 @keyframes 规则，在 @keyframes 中规定某项 CSS 样式，就能创建由当前样式逐渐改为新样式的动画效果。

> 浏览器支持
>
> Internet Explorer 10、Firefox 以及 Opera 支持 @keyframes 规则和 animation 属性。
>
> Chrome 和 Safari 需要前缀 -webkit-。

需要把@keyframes 规则捆绑到css选择器上，并在选择器里面使用animaton属性，并且至少规定两个值：动画名称，动画时长；

```css
div
{
animation: myfirst1 5s;
-moz-animation: myfirst1 5s;	/* Firefox */
-webkit-animation: myfirst1 5s;	/* Safari 和 Chrome */
-o-animation: myfirst1 5s;	/* Opera */
}

@keyframes myfirst1
{
from {background: red;}
to {background: yellow;}
}
/*请用百分比来规定变化发生的时间，或用关键词 "from" 和 "to"，等同于 0% 和 100%。*/
@keyframes myfirst2
{
0%   {background: red;}
25%  {background: yellow;}
50%  {background: blue;}
100% {background: green;}
}

```

其他属性：

- animation-timing-function：规定动画的速度曲线。默认是 "ease"。
- animation-delay：规定动画何时开始。默认是 0。
- animation-iteration-count：规定动画被播放的次数。默认是 1。
- animation-direction：规定动画是否在下一周期逆向地播放。默认是 "normal"，alternate：轮流反向
- animation-paly-state：规定动画是否正在运行或暂停。默认是 "running"。
- animation-fill-mode：规定对象动画时间之外的状态。

### 6.5 多列

通过 CSS3，您能够创建多个列来对**文本**进行布局 - 就像报纸那样

> Internet Explorer 10 和 Opera 支持多列属性。
>
> Firefox 需要前缀 -moz-。
>
> Chrome 和 Safari 需要前缀 -webkit-。
>
> 注释：Internet Explorer 9 以及更早的版本不支持多列属性。

- column-count 属性规定元素应该被分隔的列数
- column-gap 属性规定列之间的间隔
- column-rule 属性设置列之间的宽度、样式和颜色规则。

| 属性                                                         | 描述                                               | CSS  |
| ------------------------------------------------------------ | -------------------------------------------------- | ---- |
| [column-count](https://www.w3school.com.cn/cssref/pr_column-count.asp) | 规定元素应该被分隔的列数。                         | 3    |
| [column-fill](https://www.w3school.com.cn/cssref/pr_column-fill.asp) | 规定如何填充列。                                   | 3    |
| [column-gap](https://www.w3school.com.cn/cssref/pr_column-gap.asp) | 规定列之间的间隔。                                 | 3    |
| [column-rule](https://www.w3school.com.cn/cssref/pr_column-rule.asp) | 设置所有 column-rule-* 属性的简写属性。            | 3    |
| [column-rule-color](https://www.w3school.com.cn/cssref/pr_column-rule-color.asp) | 规定列之间规则的颜色。                             | 3    |
| [column-rule-style](https://www.w3school.com.cn/cssref/pr_column-rule-style.asp) | 规定列之间规则的样式。                             | 3    |
| [column-rule-width](https://www.w3school.com.cn/cssref/pr_column-rule-width.asp) | 规定列之间规则的宽度。                             | 3    |
| [column-span](https://www.w3school.com.cn/cssref/pr_column-span.asp) | 规定元素应该横跨的列数。                           | 3    |
| [column-width](https://www.w3school.com.cn/cssref/pr_column-width.asp) | 规定列的宽度。                                     | 3    |
| [columns](https://www.w3school.com.cn/cssref/pr_columns.asp) | 规定设置 column-width 和 column-count 的简写属性。 | 3    |

### 6.6 用户界面

在css3中，新的用户界面特性包括重设元素尺寸、盒尺寸以及轮廓等。

- resize 属性规定是否可由用户调整元素尺寸。

- box-sizing 属性定义了客户端应该如何计算一个元素的总宽度和总高度。

  在 [CSS 盒子模型](https://developer.mozilla.org/en-US/docs/CSS/Box_model)的默认定义里，你对一个元素所设置的 [`width`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/width) 与 [`height`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/height) 只会应用到这个元素的内容区。如果这个元素有任何的 [`border`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border) 或 [`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding) ，绘制到屏幕上时的盒子宽度和高度会加上设置的边框和内边距值。这意味着当你调整一个元素的宽度和高度时需要时刻注意到这个元素的边框和内边距。当我们实现响应式布局时，这个特点尤其烦人。

  box-sizing 属性可以被用来调整这些表现:

  - `content-box`  是默认值。如果你设置一个元素的宽为100px，那么这个元素的内容区会有100px 宽，并且任何边框和内边距的宽度都会被增加到最后绘制出来的元素宽度中。
  - `border-box` 告诉浏览器：你想要设置的边框和内边距的值是包含在width内的。也就是说，如果你将一个元素的width设为100px，那么这100px会包含它的border和padding，内容区的实际宽度是**width减去(border + padding)的值**。大多数情况下，这使得我们更容易地设定一个元素的宽高。

- outline-offset 属性对**轮廓进行偏移**，并在超出边框边缘的位置绘制轮廓。轮廓与边框有两点不同：

  - 轮廓不占用空间
  - 轮廓可能是非矩形

  | 属性                                                         | 描述                                               | CSS  |
  | ------------------------------------------------------------ | -------------------------------------------------- | ---- |
  | [appearance](https://www.w3school.com.cn/cssref/pr_appearance.asp) | 允许您将元素设置为标准用户界面元素的外观           | 3    |
  | [box-sizing](https://www.w3school.com.cn/cssref/pr_box-sizing.asp) | 允许您以确切的方式定义适应某个区域的具体内容。     | 3    |
  | [icon](https://www.w3school.com.cn/cssref/pr_icon.asp)       | 为创作者提供使用图标化等价物来设置元素样式的能力。 | 3    |
  | [nav-down](https://www.w3school.com.cn/cssref/pr_nav-down.asp) | 规定在使用 arrow-down 导航键时向何处导航。         | 3    |
  | [nav-index](https://www.w3school.com.cn/cssref/pr_nav-index.asp) | 设置元素的 tab 键控制次序。                        | 3    |
  | [nav-left](https://www.w3school.com.cn/cssref/pr_nav-left.asp) | 规定在使用 arrow-left 导航键时向何处导航。         | 3    |
  | [nav-right](https://www.w3school.com.cn/cssref/pr_nav-right.asp) | 规定在使用 arrow-right 导航键时向何处导航。        | 3    |
  | [nav-up](https://www.w3school.com.cn/cssref/pr_nav-up.asp)   | 规定在使用 arrow-up 导航键时向何处导航。           | 3    |
  | [outline-offset](https://www.w3school.com.cn/cssref/pr_outline-offset.asp) | 对轮廓进行偏移，并在超出边框边缘的位置绘制轮廓。   | 3    |
  | [resize](https://www.w3school.com.cn/cssref/pr_resize.asp)   | 规定是否可由用户对元素的尺寸进行调整。             | 3    |



未完待续...

文章的大部分内容来自w3c，学习过程中发现了很多莫名其妙的名词解释，往往看了MDN的文档才恍然大悟，当然MDN的缺点就是太详细，太啰嗦（反正我是看到一半就没有耐心了）。建议二者结合一起学习。