---
layout: post
title: Using Opacity In CSS Animations
date: '2014-02-12 14:02:36'

# Legacy
redirect_from:
    /blog/blog/using-opacity-in-css-animations/
---

When I have a free minute I sit and create CSS creatures. This often (too often perhaps) leads to excitement and the inevitable desire to make the creature do things. To move.

I created a CSS bee this week. Meet Brian. Once you create a bee, how can you not want him to fly and talk? I can't be the only one with a haunted mind. I set up a keyframe to make his wings move and to make him spin in a circle, but the opacity came into play with his face and the speech bubble.

If left to its own devises, Brian's face would appear on both sides as he turns around, and that is just simply horrifying. As a solution to this I set up a keyframe that would change the opacity from 0 to 100, enabling it to appear as if its not there at first. It was all about the timing function on this. Being set at 6 seconds provides just enough time for him to turn around, and then the animation starts. All of a sudden, FACE! There is no "infinite" added here, as he stops moving and we want him to keep his face on. Otherwise it would be the things nightmares are made of.

The speech bubble was done in a similar way but with slightly longer timing; to give him time to put his face on. I was also able to create the illusion of him opening his mouth to talk with opacity and adjusting the mouth height within a keyframe.

Brian's demo is supported by Chrome and Safari. Check out the code via the tabs below.

<p data-height="268" data-theme-id="4899" data-slug-hash="AEhxd" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/AEhxd'>Brian The CSS Bee</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>

Happy transparency-ing!
