---
layout: post
title:  "Truth Tables for Conditional Statements"
date:   2014-07-30 01:17:00
categories:
- blog
- ENS1161
---

My brain completely melted when I first looked at the content for this unit. I never really saw anything like `((r → (q → p)) ^ ~p) → ~r` before and I nearly done shat myself. But after a couple of days, I'm starting to get the hang of it. 

The thing that took awhile to get my head around though, was how to figure out if `r → p` was `true` or `false`.

Let's say `r` = You rob a bank.

And `p` = Get paid.

In plain English, `r → p` translates to:

>`If` you rob a bank `then` you get paid.

So think of `r` (or whatever is before the `→`) like a job you need to do, and `p` (or whatever is after the `→`) is the reward for doing the job.

If `r` is `true`, you did the job. If `r` is `false`, then you haven't done it... Whats wrong? You gone soft mate?

Then on the other side of `→`, if `p` is true, you either *can* or *will* get the reward. It's available to you whether or not you've done the job. But... if `p` is false, then the reward is not available, and you might be getting ripped off.

Don't get played. Nobody got time for that. And that's when the statement is `false`.

<!--more-->

**Let's go through the possible scenarios:**

1. `r` is `true` so you did the job, and `p` is true so you gots paid.
	- Time to make it rain at your local strip club and mark off the conditional statement as `true`.
2. `r` is `false` so you pussied out, and `p` is true so the cash is sitting there waiting for you.
	- But you didn't deserve the money anyway. Mark off the conditional statement as `true`.
3. `r` is `false` so the job didn't happen, but `p` is false too so there's no cash to begin with.
	- All good, we can live with that. We'll just mark that scenario `true` anyway since there's no harm or foul. 
4. `r` is `true` so you did the job, but `p` is false. Wait hold up... Where's the money?
	- You got jacked. Any time you get ripped off, mark the conditional statement as `false`. 

Here's where I got the initial idea anyway. He probably explains it a lot better.

<iframe width="640" height="360" src="http://www.youtube.com/embed/2npo-L0DJRQ" frameborder="0" style="margin-bottom: 20px;"></iframe>