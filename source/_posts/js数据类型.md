---
title: js数据类型
date: 2019-05-14 22:22:09
tags:
---


### JS的数据类型

#### JS的数据类型有 String, Number, Boolean, Null, Undefined, Objcet

1. String
 String为字符串类型,代表的就是字符串.通常用双引号 或者 单引号
 如 'a' 或 "b"

2. Number
Number为数字类型, 代表数字.  常用的为十进制. 
前缀为```0b```表示二进制 如: ```0b11``` 代表十进制的3.
前缀为```01``` 表示八进制 如: ```011``` 代表十进制的9.

3. Boolean
Boolean类型有 ```true```和```false```两个值.    
这里会有 && 和 || 的布尔值运算
a && b 和 a || b   
&&两true为true 其余为false
||一个为true就是true


4. Null
Null就是代表空值,js中 使用```typeof null``` 会出现```'objcet'```的情况,这是js的bug.根据我查到的资料 是这样的
>>> 在 JS 的最初版本中使用的是 32 位系统，为了性能考虑使用低位存储变量的类型信息，000 开头代表是对象，然而 null 表示为全零，所以将它错误的判断为 object 。
5. Undefined
undefined类型只有undefined这个值.也是代表空值.和null区别如下:
 变量声明未赋值为undefined
 想要将变量赋值为对象,初始化赋值用null.如: ```var a = null```这样大家就知道a这个变量想作为变量使用了
 而undefined正好相反, 变量不想赋值为对象 那就直接声明变量 不用赋值即可.
6. Object
object类型的值是由基本类型组成的.
是key-vaule键值对的形式.如: 

``` javascript   
var obj = {
  a: '1',
  b: '2'
}
```
可以通过 obj.a, obj['a']访问值
