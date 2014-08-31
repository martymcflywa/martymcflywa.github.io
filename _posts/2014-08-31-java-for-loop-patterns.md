---
layout: post
title:  "Java For Loop Patterns"
date:   2014-08-31 23:35:00
categories:
- blog
- CSP1150
---

One of the assessments for this week's programming unit was to print the following patterns using only two nested `for` loops in the console.

```
*****  *****  **+**  **+**
*****  *****  **+**  **+**
*****  +++++  **+**  +++++
*****  *****  **+**  **+**
*****  *****  **+**  **+**
```

The first pattern was easy, but I had a hell of a time figuring out how to print the patterns with `+`.

Then I remembered that you can use an `if` statement to determine whether or not a column or row needs to print `+` instead of `*`.

So here's my method which prints the last pattern:

{% highlight java %}
static void patternD() {
		
	System.out.println("Pattern D\n");
	
	// iterate each row of BASE_SIZE
	for(int row = 0; row < BASE_SIZE; row++) {
		
		// iterate each column of BASE_SIZE
		for(int col = 0; col < BASE_SIZE; col++) {
			
			// if row OR col == CROSS_POS, print "+"
			if(row == CROSS_POS || col == CROSS_POS) {
				System.out.print("+");
			
			// else print "*"
			} else {
				System.out.print("*");
			}
		}
		
	// return cursor to next line for each row of BASE_SIZE
	System.out.println();
	}
}
{% endhighlight %}

<!--more-->

So the `if` statement inside the second loop checks whether or not `row` OR `col` is the same as `CROSS_POS`, which in this case was `2`. If it is, then `+` is printed. If it isn't, `*` is printed instead, resulting in the fourth pattern shown above.

Here's a video that explains it very well at around [6:33](http://youtu.be/DoUdYh9V5aQ?t=6m33s).

<iframe width="640" height="360" src="http://www.youtube.com/embed/DoUdYh9V5aQ?t=6m33s" frameborder="0" style="margin-bottom: 20px;"></iframe>