---
layout: post
title: SVG Sprites and Icon Systems Are Super
date: '2015-03-03 16:06:54'

# Legacy
redirect_from:
    /blog/blog/svg-sprites-and-icon-systems-are-super/
---

I wrote a post over at [Lincoln Loop](https://lincolnloop.com/) recently on using SVG sprites as an icon system: *[SVG Sprites and Icon Systems Are Super](https://lincolnloop.com/blog/svg-sprites-and-icon-systems-are-super/)*. The post was a response to an email I received asking about how to use *a lot* of SVG icons and be able to change their colors with CSS, but also not have all that markup that goes along with inline SVG.

![Screenshot of icon sprite demo](/content/2015/Feb/Screen-Shot-2015-02-25-at-10-55-57-AM.png)

The problem, as I understand it, is that he needs access to the SVG's "innards" to be able to change the fill color, and therefore not having to include twice as many icons as you would have to do with images but also not have bunches of inline SVG code sitting around.

When you use an SVG as an img you cannot then go "in" to the SVG and change its fill or stroke with CSS.

![alt](/content/2015/Mar/asimagevisual_1024.png)

This would very quickly prove frustrating and inefficient when working with so many icons. Accessing the fill of these icons to change the palette for color blind users, for example, would be impossible and you would therefore need additional images.

In the response post I proposed using SVG sprites, which is something I [read all about last year on CSS-Tricks](https://css-tricks.com/svg-sprites-use-better-icon-fonts/). It's super clever and really results in the best of both worlds between using an <code>img</code> (less markup!) and inline SVG (complete control!).
