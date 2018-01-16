---
layout:     post
title:      css3中单位px,em,rem,vh,vw,vmin,vmax的区别及浏览器支持情况
subtitle:   css3中单位px,em,rem,vh,vw,vmin,vmax的区别及浏览器支持情况
date:       2018-01-09
author:     BY Liuxia
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    - css3
    - px
    - vh
---  

  
**# px #**：绝对单位，页面按精确像素展示  

**# em #**：相对单位，基准点为父节点字体的大小，如果自身定义了font-size按自身来计算（浏览器默认字体是16px），整个页面内1em不是一个固定的值。  

**# rem #**：相对单位，可理解为”root em”, 相对根节点html的字体大小来计算，CSS3新加属性，chrome/firefox/IE9+支持。  

(另外需注意chrome强制最小字体为12号，即使设置成 10px 最终都会显示成 12px，当把html的font-size设置成10px,子节点rem的计算还是以12px为基准，所以网上很多文章提到的将html的font-size设为10方便计算不是那么可取)。  

rem在移动端应用可参考淘宝的页面http://m.taobao.com (html的font-size通过动态计算获取)  

页面基准320px(20px),html font-size值的计算：  

[javascript] view plain copy

	1. var ele=document.getElementsByTagName("html")[0],  
	2.      size=document.body.clientWidth/320*20;  
	3. ele.style.fontSize=size+"px"  

注：需设置meta缩放比1:1  

``` 
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0, user-scalable=no" />

```


vw：viewpoint width，视窗宽度，1vw等于视窗宽度的1%。  

vh：viewpoint height，视窗高度，1vh等于视窗高度的1%。  

vmin：vw和vh中较小的那个。  

vmax：vw和vh中较大的那个。  

vw, vh, vmin, vmax：IE9+局部支持，chrome/firefox/safari/opera支持，ios safari 8+支持，android browser4.4+支持，chrome for android39支持  


其它的单位还有：  

%:百分比  

in:寸  

cm:厘米  

mm:毫米  

pt:point，大约1/72寸  

pc:pica，大约6pt，1/6寸  


ex：取当前作用效果的字体的x的高度，在无法确定x高度的情况下以0.5em计算(IE11及以下均不支持，firefox/chrome/safari/opera/ios safari/android browser4.4+等均需属性加么有前缀)  

ch:以节点所使用字体中的“0”字符为基准，找不到时为0.5em(ie10+,chrome31+,safair7.1+,opera26+,ios safari 7.1+,android browser4.4+支持)  


参考资料：  

http://dev.w3.org/csswg/css-values/#font-relative-lengths  

http://isux.tencent.com/web-app-rem.html  



