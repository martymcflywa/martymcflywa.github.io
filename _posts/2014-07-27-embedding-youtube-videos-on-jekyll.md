---
layout: post
title:  "Embedding Youtube Videos on Jekyll"
date:   2014-07-27 11:56:19
categories:
- blog
---

For future reference, here's how to embed youtube videos on Jekyll:

{% highlight html %}
<iframe width="640" height="360" src="http://www.youtube.com/embed/YOUTUBEID" frameborder="0" style="margin-bottom: 20px;"></iframe>
{% endhighlight %}

Note the inline style for `margin-bottom`. Might need to remove the inline style and add custom CSS if I decide to change or customise this theme later.