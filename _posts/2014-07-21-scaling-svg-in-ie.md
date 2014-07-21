---
layout: post
title:  "Scaling SVG in Internet Explorer"
date:   2014-07-21 22:43:15
categories: web development
---

Came across another issue with SVGs in IE 9. Chrome scaled them beautifully according to the window width but IE didn't. Why?? After some quick googling, I came across this [stackoverflow](http://stackoverflow.com/questions/7711641/why-doesnt-this-svg-graphic-scale-in-ie9-and-10-preview) question regarding the same issue. 

The answer is to add `preserveAspectRatio="xMinYMin slice"` attribute to the SVG, like so:

{% highlight html %}
<?xml version="1.0" encoding="utf-8"?>
<svg 
	version="1.1" 
	id="logo" 
	xmlns="http://www.w3.org/2000/svg" 
	xmlns:xlink="http://www.w3.org/1999/xlink" 
	viewBox="0 0 113.941 88.432" 
	preserveAspectRatio="xMinYMin slice" 
	xml:space="preserve">

	// define path, polygon etc here
	
</svg>
{% endhighlight %}

No visible impact to webkit so far, but we shall see.