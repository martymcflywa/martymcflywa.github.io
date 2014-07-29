---
layout: post
title:  "Internet Explorer, why you suck?"
date:   2014-07-21 21:50:47
categories: web development
---

But it probably doesn't... it's just me, probably.

After a fairly long break in web design, or any design for that matter, I was recently referred to someone to help them redesign their website/e-store which runs on Wordpress and uses the Woocommerce plugin for their store. I figured it would be a good opportunity to brush up on my design skills and learn some new tricks. The deadline is fairly loose since they already have a current site, so I decided to go with using SVGs to display their brand spanking new logo that I designed, as well as masking some elements with SVG to create some curved lines in the layout.

<!--more-->

So for most of my time spent developing their theme so far, I was using Chrome to preview. After a week into coding, I fired up IE 9 to take a look and was sorely disappointed in what I saw. So here's what I should have done.

>Preview on as many browsers as possible... from the start.

I had to fix it, and couldn't figure out how to use SVGs to mask elements in IE. But I had to move on, so I wrote some ie conditionals to display .png files instead (probably not the best thing to do?). But those conditionals broke the pixel perfect design I sculpted into Chrome.

Originally, I had this:

{% highlight html %}
<!--[if IE]>
<div id="ie-bottom-curve">
	<img src="<?php bloginfo('template_directory');?>/inc/img/ie/curvebottom.png">
</div>
<![endif]-->

<!--[if !IE]>
<div id="curve-bottom-container">
	<?php include ('inc/img/svg/curveouterbottom.svg'); ?>
</div>
<![endif]-->
{% endhighlight %}

Which resulted in #curve-bottom-container never showing up in Chrome. The !IE condition syntax was wrong and wound up commenting out that block. It should have been obvious due to the syntax highlighting, or lack thereof.

The !IE condition really should have been written like this:

{% highlight html %}
<!--[if !(IE)]><!-->
<div id="curve-bottom-container">
	<?php include ('inc/img/svg/curveouterbottom.svg'); ?>
</div>
<!--<![endif]-->
{% endhighlight %}

Thank god, SVG back up. There's obviously still a lot I need to learn.