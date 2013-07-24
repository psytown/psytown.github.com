---
layout: post
title: jQuery调用JSON
category: posts
---

今天在做sidebar分值列表的时候，想到用jQuery调用JSON数据，在做的过程中，发现其实里面蕴含两个知识点：

1. 调用JSON文件方法
2. 如何调取JSON内Object、Array的不同数据形式

####调用JSON文件
调用还是比较简单的，通过$.get()方式，官方文档详见[这里](http://api.jquery.com/jQuery.getJSON/)

		$.getJSON(url,data,callback)
		
		例1：callback为调用某函数
		$.getJSON(data.json,'someDataSet',someFunction)
		
		function someFunciton(data){
		  ///balalala
		}
		
		例2：callback直接使用函数
		$.getJSON(data.json,'someDataSet',function(data) {
		////balalalla
		});
		
		
####如何调取不同数据形式
需要特殊记录一下在数组中取值，我们在没有string头的情况下，需要定位array的index

		json.users[3].name