---
title: 常见html标签的使用
date: 2019-03-04 20:59:18
categories: 学习笔记
tags: 
- HTML
---
## 1. &lt;iframe&gt; 
HTML内联框架元素 &lt;iframe&gt; 表示嵌套的浏览上下文，有效地将另一个HTML页面嵌入到当前页面中。   
也就是说&lt;iframe&gt;这个标签通常用作显示网页使用   
常见的属性：

属性 | 作用
------------ | :-------------:
frameborder | 取值为1时（默认值），告诉浏览器在当前iframe与其他iframe之间绘制边框，取0时则无需绘制此边框。
height | 以CSS像素格式指定frame的高度。
name  | 嵌入的浏览上下文（框架）的名称。该名称可以用作&lt;a&gt;标签，&lt;form&gt;标签的target属性值，或&lt;input&gt; 标签和 &lt;button&gt;标签的formtaget属性值。
src | 嵌套页面的URL地址。使用遵守同源策略的  'about:blank' 来嵌套空白页。
width | 以CSS像素格式或以百分比格式指定frame的宽度。

&lt;iframe&gt;属于可替换元素(在 CSS 中，可替换元素（replaced element）的展现效果不是由 CSS 来控制的。这些元素是一种外部对象，它们外观的渲染，是独立于 CSS 的。).


## 2. &lt;a&gt;    
HTML &lt;a&gt; 元素（或称锚元素）可以创建通向其他网页、文件、同一页面内的位置、电子邮件地址或任何其他 URL 的超链接。(可用于提交get请求)

常用属性：  

属性 | 作用
------------ | :-------------:
href |  包含超链接指向的 URL 或 URL 片段。URL 不限于基于 Web（HTTP）的文档，也可以使用浏览器支持的任何协议。例如，在大多数浏览器中正常工作的file:
rel  |  该属性指定了目标对象到链接对象的关系。该值是空格分隔的列表类型值
target  |  该属性指定在何处显示链接的资源。 取值为标签（tab），窗口（window），或框架（iframe）等浏览上下文的名称或其他关键词。

target关键词：
  - _self: 当前页面加载，即当前的响应到同一HTML5浏览上下文。此值是默认的，如果没有指定属性的话。
  - _blank: 新窗口打开，即到一个新的HTML5浏览器上下文
  - _parent: 加载响应到浏览上下文的父浏览上下文。如果没有parent框架或者浏览上下文，此选项的行为方式与 _self 相同。
  - _top: 加载响应进入顶层浏览上下文（即，浏览上下文，它是当前的一个的祖先，并且没有parent）。如果没有parent框架或者浏览上下文，此选项的行为方式相同_self    



## 3.  &lt;form&gt;  

HTML &lt;form&gt; 元素 表示了文档中的一个区域，这个区域包含有交互控制元件，用来向web服务器提交信息。(通常用于提交post请求)  

常用属性：


属性 | 作用
------------ | :-------------:
method | 浏览器使用这种 HTTP 方式来提交 form. 可能的值有:post/get:这个值可以被 &lt;button&gt; 或者 &lt;input&gt; 元素中的 formmethod 属性重载（覆盖）
name  |  这个form的名字。HTML5中，一个文档中的多个form当中，name必须唯一而不仅仅是一个空字符串。


## 4. &lt;input&gt; / &lt;button&gt;   
HTML &lt;input&gt; 元素用于为基于Web的表单创建交互式控件，以便接受来自用户的数据; 可以使用各种类型的输入数据和控件小部件，具体取决于设备和user agent。  
HTML &lt;button&gt; 元素表示一个可点击的按钮，可以用在表单或文档其它需要使用简单标准按钮的地方。 默认情况下，HTML按钮的显示样式接近于 user agent 所在的宿主系统平台（用户操作系统）的按钮， 但你可以使用 CSS 来改变按钮的样貌。

&lt;input&gt;标签为空标签(一个空元素（empty element）可能是 HTML，SVG，或者 MathML 里的一个不可能存在子节点（例如内嵌的元素或者元素内的文本）的element。)

input的type:
- checkbox： 复选框。必须使用 value 属性定义此控件被提交时的值。使用 checked 属性指示控件是否被选择。
- date：HTML5 用于输入日期的控件（年，月，日，不包括时间）。
- file：此控件可以让用户选择文件。使用 accept 属性可以定义控件可以选择的文件类型。
- hidden：不显示在页面上的控件，但它的值会被提交到服务器。
- image：图片提交按钮。必须使用 src 属性定义图片的来源及使用 alt 定义替代文本。还可以使用 height 和 width 属性以像素为单位定义图片的大小。
- month：HTML5 用于输入年月的控件，不带时区。
- number: HTML5 用于输入浮点数的控件。
- password：一个值被遮盖的单行文本字段。使用 maxlength 指定可以输入的值的最大长度 。
- radio：单选按钮。必须使用 value 属性定义此控件被提交时的值。使用checked 必须指示控件是否缺省被选择。在同一个”单选按钮组“中，所有单选按钮的 name 属性使用同一个值； 一个单选按钮组中是，同一时间只有一个单选按钮可以被选择。    

button的type：   

- submit:  此按钮将表单数据提交给服务器。如果未指定属性，或者属性动态更改为空值或无效值，则此值为默认值。
- reset:  此按钮重置所有组件为初始值。
- button: 此按钮没有默认行为。它可以有与元素事件相关的客户端脚本，当事件出现时可触发。
- menu: 此按钮打开一个由指定&lt;menu&gt;元素进行定义的弹出菜单。


## 5. &lt;table &gt;   
HTML的 table 元素表示表格数据 — 即通过二维数据表表示的信息。  
允许的内容： 按照这个顺序
- 一个可选的 &lt;caption&gt; 元素
- 零个或多个的 &lt;colgroup&gt; 元素
- 一个可选的 &lt;thead&gt; 元素
- 一个可选的 &lt;tfoot&gt; 元素（tfoot元素出现在tbody或tr元素前后都可以。在HTML4中，它只能出现在这些元素之前）
- 零个或多个 &lt;tbody&gt; 元素
- 一个或多个 &lt;tr&gt; 元素