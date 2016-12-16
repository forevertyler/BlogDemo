<h1 style="font-size: 40px;text-align:center;color: #007cdc;">
    style、currentStyle、getComputedStyle区别介绍
</h1>

####  __样式表有三种方式__

 __内嵌样式__ （inline Style） ：是写在Tag里面的，内嵌样式只对所有的Tag有效。

 __内部样式__ （internal Style Sheet）：是写在HTML的里面的，内部样式只对所在的网页有效。

 __外部样式表__（External Style Sheet）：如果很多网页需要用到同样的样式(Styles)，将样式(Styles)写在一个以.css为后缀的CSS文件里，然后在每个需要用到这些样式(Styles)的网页里引用这个CSS文件。 最常用的是style属性，在JavaScript中，通过document.getElementById(id).style.XXX就可以获取到XXX的值，但意外的是，这样做只能取到通过内嵌方式设置的样式值，即style属性里面设置的值。

  __解决方案：__  引入currentStyle,runtimeStyle,getComputedStyle style 标准的样式,可能是由style属性指定的！

runtimeStyle 运行时的样式！如果与style的属性重叠，将覆盖style的属性！

currentStyle 指 style 和 runtimeStyle 的结合！ 通过currentStyle就可以获取到通过内联或外部引用的CSS样式的值了（仅限IE） 如：document.getElementById("test").currentStyle.top

要兼容FF，就得需要getComputedStyle 出马了

注意: getComputedStyle是firefox中的， currentStyle是ie中的. 比如说

````CSS
#mydiv {
  width : 300px;
  height: 300px;
  background-color: teal;
}
````

则：

````js
var mydiv = document.getElementById('mydiv');
if(mydiv.currentStyle) {
      var width = mydiv.currentStyle['width'];
      alert('ie:' + width);
} else if(window.getComputedStyle) {
      var width = window.getComputedStyle(mydiv , null)['width'];
      alert('firefox:' + width);
}
````

另外在FF下还可以通过下面的方式获取
````js
document.defaultView.getComputedStyle(mydiv,null).width;
window.getComputedStyle(mydiv , null).width;
````
