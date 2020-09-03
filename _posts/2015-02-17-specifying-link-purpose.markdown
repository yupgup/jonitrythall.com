---
layout: post
title: Specifying Link Purpose
date: '2015-02-17 18:15:56'

# Legacy
redirect_from:
    /specifying-link-purpose/
---

![Screenshot of demo showing three different links with the same text but representing different things.](/content/2015/Feb/Screen-Shot-2015-02-17-at-12-08-12-PM.png)

I read a [brief acticle recently](https://www.ssbbartgroup.com/blog/2015/01/09/indicating-link-purpose-with-aria/) that discusses the complications brought about by having a number of links on a page represented by the same text.

While users without disabilities will mostly be able to decipher the different intentions of these links based on the page's content, these intentions become much less clear for users with disabilities. If there are a series of links with the same text, how can we label these and make them more distinguishable?

### ARIA

[Accessible Rich Internet Applications (ARIA)](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) defines ways to make web content more accessible to people with disabilities. ARIA provides a set of special accessibility attributes that we can add to our HTML.

There are three proposed solutions to this issue using [ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) in the article mentioned above: aria-describedby, aria-labelledby, and aria-label. Including one of these within similar links can help associate it with something more distinguishable, such as the fruit images in the demo below.

We will focus on just one of these in the demo, aria-label.

### Demo

To demonstrate a more accessible solution here let's look at a list of menu options sorted by ingredients, all with the same text, "View Items".

<p data-height="294" data-theme-id="11708" data-slug-hash="8e39840347052181d014064d7648c58b" data-default-tab="result" data-user="jonitrythall" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/8e39840347052181d014064d7648c58b/'>Indicating Link Purpose</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

If you take a peek at the HTML, each link includes an ARIA attribute that helps better describe it, explaining its uniqueness from the other potentially seemingly identical links. For example, here's a look at the link associated with the apple:

	<a href="#" aria-label="View Items- Apple items">View Items</a>

While this is a very small glimpse at a use case for a specific ARIA attribute and *loads* of other things to keep in mind in terms of accessibility, it's something I thought was pretty neat and will be sure to keep in mind in the future when using a series of links with the same text.
