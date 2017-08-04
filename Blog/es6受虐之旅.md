<h1 style="font-size: 40px;text-align:center;color: #007cdc;font-weight: bold;">
    ES6受虐之旅
</h1>

###  从今天开始重新整理学习ES6



<h2 style="font-weight: bold;">箭头函数【Arrow function】</h2> 

#### 概述

###### ES6的箭头函数的特点：永远是匿名函数，并且增加了ES5所没有的一些优点


###### //ES5

````js

var tt = function tt(){
	return 1 + 1;
}
````

###### //ES6

````js
var tt = () => 1 + 1  //是不是一对比，写法的差异就看出来了
````

#### 用法汇总

###### ES5匿名函数的用法

````js
var testArr = [1,2,3,4,5,6];
var test = testArr.reduce(function (previous,current,index,array{
	console.log(previous);//累加值
	console.log(current);//当前位的数组值
	console.log(index);//元素在数组中的索引
	console.log(array);//调用reduce的数组
	return previous + current
}))//结果集：21
````

#### ES6箭头函数

````js
var test = testArr.reduce((previous,current,index,array) => {
	console.log(previous);//累加值
	console.log(current);//当前位的数组值
	console.log(index);//元素在数组中的索引
	console.log(array);//调用reduce的数组
	return previous + current
})//结果集：21
````

*** 注意点 ***

1.一个参数的可以不带括号直接作用

- 没有参数的必须带小括号

- 多条执行语句需花括号包裹

- 字面量对象的返回需要小括号包裹！！！！

- `this` 强制绑定（定义绑定），普通函数是用时绑定 `(apply,call,bind)` ; 箭头函数的 `this` 不等同于 `usestrict` 模式下的 `this`

