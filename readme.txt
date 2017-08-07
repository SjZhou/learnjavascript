Learning Javascript:
1)数据类型比较：
false==0;  //true
false===0; //false
== 比较，它会自动转换类型比较。
=== 不会自动转换类型比较，如果类型不一致，返回false，如果一致，再比较。

2)NaN(Not a Number)[NaN 是个特殊的Number,与所有其他值都不相等，包括它自己]
NaN===NaN; // false
唯一能判断NaN 的方法是通过isNaN()函数：
isNaN(NaN); //true

3)浮点数的比较：
1/3 === (1-2/3); //false
浮点数在运算过程中会产生误差，因为计算机无法精确表示无限循环小数。要比较两个浮点数是否相等，只能计算它们的绝对值，看是否小于某个阈值：
Math.abs(1/3-(1-2/3))<0.0000001; //true

4)null和undefined
null表示一个"空"的值，它和0以及空字符串''不同，0是一个数值，''表示长度为0的字符串，而null表示"空"；
undefined 表示"未定义"
区分两者的意义不大。大多数情况下，我们都应该用null。undefined 仅仅在判断函数参数是否传递的情况下有用。

5)数组 - 数组是一组按顺序排列的集合，集合的每个值称为元素。JavaScript的数组可以包括任意数据类型。例如：
[1, 2, 3.14, 'Hello', null, true];
上述数组包含6个元素。数组用[]表示，元素之间用,分隔。
另一种创建数组的方法是通过Array()函数实现：
new Array(1, 2, 3); // 创建了数组[1, 2, 3]
然而，出于代码的可读性考虑，强烈建议直接使用[]。
数组的元素可以通过索引来访问。请注意，索引的起始值为0：
var arr = [1, 2, 3.14, 'Hello', null, true];
arr[0]; // 返回索引为0的元素，即1
arr[5]; // 返回索引为5的元素，即true
arr[6]; // 索引超出了范围，返回undefined

6)对象 - JavaScript的对象是一组由键-值组成的无序集合，例如：
var person = {
    name: 'Bob',
    age: 20,
    tags: ['js', 'web', 'mobile'],
    city: 'Beijing',
    hasCar: true,
    zipcode: null
};
JavaScript对象的键都是字符串类型，值可以是任意数据类型。上述person对象一共定义了6个键值对，其中每个键又称为对象的属性，例如，person的name属性为'Bob'，zipcode属性为null。
要获取一个对象的属性，我们用对象变量.属性名的方式：
person.name; // 'Bob'
person.zipcode; // null

7)strict模式 - JavaScript在设计之初，为了方便初学者学习，并不强制要求用var申明变量。这个设计错误带来了严重的后果：如果一个变量没有通过var申明就被使用，那么该变量就自动被申明为全局变量：
i = 10; // i现在是全局变量
在同一个页面的不同的JavaScript文件中，如果都不用var申明，恰好都使用了变量i，将造成变量i互相影响，产生难以调试的错误结果。
使用var申明的变量则不是全局变量，它的范围被限制在该变量被申明的函数体内（函数的概念将稍后讲解），同名变量在不同的函数体内互不冲突。
为了修补JavaScript这一严重设计缺陷，ECMA在后续规范中推出了strict模式，在strict模式下运行的JavaScript代码，强制通过var申明变量，未使用var申明变量就使用的，将导致运行错误。
启用strict模式的方法是在JavaScript代码的第一行写上：

'use strict';

这是一个字符串，不支持strict模式的浏览器会把它当做一个字符串语句执行，支持strict模式的浏览器将开启strict模式运行JavaScript。