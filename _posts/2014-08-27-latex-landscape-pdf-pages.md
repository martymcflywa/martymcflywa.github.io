---
layout: post
title:  "LaTeX Landscape PDF Pages"
date:   2014-08-27 09:54:00
categories:
- blog
- CSG1132
---

So I wasn't quite happy with the way my concept map was being displayed on the page. For starters, it was a raster image and did not scale well to A4 landscape. The positioning was doing some funny things too so I decided to try adding it as a PDF page instead. The only issue with that though, was the page did not rotate in the viewer, which might have been a problem for submission. This issue was caused by wrapping the `\includepdf` command inside `\begin{figure}`. So I broke it out of the wrap, which then broke my `fancyhdr` custom preset.

Here's how I fixed it.

{% highlight latex %}
\documentclass[12pt, a4paper]{report}
\usepackage{pdflscape}
\usepackage{pdfpages}
\usepackage{fancyhdr}
\usepackage[absolute]{textpos} % can also have showboxes as argument

% defining fancyhdr parameters
\pagestyle{fancy}
\fancyhf{} % clears any header / footer
	\lhead{Insert left header here}
	\rhead{Insert right header here}
	\lfoot{Insert left footer hear}
	\rfoot{\thepage} % adds page number as right footer

% define landscape header / footer
\fancypagestyle{fancylscape}{ % give it a name here
	% whatever parameters and positioning you want here
}

\begin{document}
	\begin{landscape} % needed this to turn the caption 90*
		% added empty figure just for the caption
		\begin{figure}
			\centering
			\caption{Concept map}
		\end{figure}
	% pdf page inserted here
	\includepdf[landscape, turn=true, pagecommand={\thispagestyle{fancylscape}}]{./img/filename.pdf}
	\end{landscape}
\end{document}
{% endhighlight %}

<!--more-->

The arguments for `\includepdf` allow for command execution with `pagecommand={}` which I thought was pretty neat. Here you can call your custom `fancyhdr` preset, which in this case is called `fancylscape`.

`turn=true` is another important argument, as this turns the logical page (inside the viewer) to landscape, rather than just leaving the page as 'portrait' and turning everything inside it 90 degrees.

Page rotated, image embedded as vector, fancy footers / headers included and rotated along with the page. Win.

Time to submit my assignment.