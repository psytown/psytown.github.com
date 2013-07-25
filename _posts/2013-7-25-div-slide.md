---
layout: post
title: 实现对div的slide效果
category: posts
---

想把报告的分页过渡做的有趣一些，并且也适合pad端的阅读，slide效果是最为自然的一种实现方式，我们可以在很多产品中看到slide的影子，最为普遍的slide图片，这个在各大中小网站都可以看到slidebanner，另外一种则是[Erly](http://erly.com/)的那种横版slide效果，后来国内纯银团队的蝉游记借鉴，这种slide是对div进行整体的滑动。

在google和github上找了一些slide的方案，基本搜索的话会分为三大类
 
 1. 移动端的slidemenu，最火的一些repo
 2. 传统对图片的slide
 3. 对div的slide效果 
 
在试用多个不靠谱的方案后，最后发现[Liquid Slider 2 ](http://liquidslider.com/)比较符合自己的预期效果，看了一眼github，这哥们几分钟前刚更新过，靠谱。

####Trial process


1. 新建测试文档
		
	由于之前的文档中编辑d3和jQuery，还没有剥离js出来，索性新建一个test.html只包含到container层的新文件

2. 安装

   [Liquid Slider Examples](http://kevinbatdorf.github.io/liquidslider/examples/page1.html)在examples页面，看如何install，比较简单，就是download之后引入相关的文件。需要注意的是，里面除了引用还需要引一段function代码，查看其文档后得知，相关的配置可在该函数中进行修改。
   
		<script>
		$(function(){
     	$('#slider-id').liquidSlider();
		});
		</script>

   注：“#silder-id”为你想slide的div集的最高级div的id名，可更换为其他，引入的js文件会在该div集中进行class等各种属性的添加，来实现其slide效果，所以html中的代码很简单都是
   
   	   <div class="liquid-slider" id="slider-id">
       <div>
          <h2 class="title">Slide 1</h2>
          // Content goes here
       </div>
       <div>
          <h2 class="title">Slide 2</h2>
          // Content goes here
       </div>
       <div>
          <h2 class="title">Slide 3</h2>
          // Content goes here
       </div>
       </div>

3. 配置
   
   配置需要查看都有什么功能，一个是看example中的例子，另一个是看[Documentation](http://liquidslider.com/documentation/)，配置方法就是在添加的function函数代码中添加相应的true或者false来进行相关功能的开启和闭合，比如想使用键盘控制slide的滑动，则添加如下：
   
   		<script>
		$(function(){
     	$('#slider-id').liquidSlider({
     	
     	keyboardNavigation: true
     	
     	});
		});
		</script>

	然后就能用键盘控制slide了
4. 定制
   和bootstrap一样，可以根据不同的选择来进行[Custom Build](http://liquidslider.com/custom-build/)，选择完之后，会生成相应的demo文件夹，包括html、js、css和img。
   不过奇怪的是，选择后替换js，但并不是默认，而是还要再function中开启相关配置，也许可能是没找对地方，再之后开发时再注意一下吧


5. swipe功能
   里面swipe功能对于移动端用户是非常有用的，移动端键盘就不起作用了，可以用滑屏来操作slide，想支持滑屏，需要安装[mattbryson/TouchSwipe-Jquery-Plugin](https://github.com/mattbryson/TouchSwipe-Jquery-Plugin)。
   
在想有没有什么服务器插件能够在同wifi下，使用pad访问机器上的网页，grunt可以么？
   
   
 


