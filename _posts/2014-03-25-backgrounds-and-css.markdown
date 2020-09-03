---
layout: post
title: CSS Animation Delays
date: '2014-03-25 22:24:53'

# Legacy
redirect_from:
    /blog/blog/backgrounds-and-css/
---

I recently had to use multiple CSS animation delays and wanted to create a quick demo to, you know, demonstrate.

For this demo I created a series of circles. These circles were to communicate gradual progress states via background change. The circles start out with a rotating multi colored background and then gradually all change to solid green, signalling completion.  

While I want the rotation animation to start right away for each circle, the color change has to be delayed by different times within each circle.  

The solution here is fairly simple but it excited me to an inappropriate level: multiple delays separated by commas. Let's take a look at the animation assignment for the second circle for an example:

    .dot-2:after {
      animation: turn 8ms infinite, complete 1s forwards;
      animation-delay: 0, 10s;
    }

The progress circles demo is for Chrome and Safari eyeballs only.

<p data-height="268" data-theme-id="4899" data-slug-hash="9dc37883fce3c4641c51ee0f777744a8" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/9dc37883fce3c4641c51ee0f777744a8/'>CSS Progress Circles</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>

You can add multiple animation delays that coordinate with multiple animations. So flippin’ cool.


Happy multiple delaying!
