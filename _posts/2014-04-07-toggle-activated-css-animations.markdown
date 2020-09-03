---
layout: post
title: Switch Activated CSS Animations
date: '2014-04-07 15:59:21'

# Legacy
redirect_from:
    /toggle-activated-css-animations/
---

I created two demos to show how animations can be activated via switch. One demo animates an "Airplane Mode" experience and the other contains a series of street lamps that will turn on. So let's take a look.

<p data-height="268" data-theme-id="4899" data-slug-hash="sKIqm" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/sKIqm/'>Toggled Airplane Mode Animation</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>

<p data-height="268" data-theme-id="4899" data-slug-hash="DuIrq" data-default-tab="result" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/DuIrq/'>Street Lamps With Switch</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//codepen.io/assets/embed/ei.js"></script>

The first step after setting up your `@keyframes` is to create the switch, which we will do by styling a checkbox `<input>` into a toggle. The button slides within a styled `<label>` and the button itself is created and styled using `label:after`.

Once the styling is complete we need to set up the sliding effect. We want the button to move to the right once clicked, so we will set up an animation and assign it using `:checked`.

    input:checked + label:after {
      animation: slide 1s forwards;
    }

    @keyframes slide {
      to {
        transform: translateX(50px);
      }
    }

We are declaring that after the checkbox (although visually we have created something different) is clicked, the button should move to the right 50px.

After the switch is established we can set up our animation assignments. Let's look at the street lights demo for this specifically.

    input:checked ~ .sky  {
      animation: brightness 5s forwards;
    }

    input:checked ~ .contain-lamp .light  {
      animation: light 6s forwards;
    }

    input:checked ~ .contain-lamp .top-base:after  {
      animation: glare 9s forwards;
    }

When the toggle is clicked, the following elements will be selected and the animation will be carried out on those elements. For selection purposes, it's important that the animated element is a sibling of `<input>` or contained within an element that is a sibling.

Concerning the "Airplane Mode" demo, I originally had tried to recreate [this CSS "mouse out" effect](http://jonibologna.com/animated-twitter-button/) to keep the airplane "off" animation from playing on page load with `:not(:checked)`, but quickly realized that it wouldn't work. `:not(:checked)` initially seemed like it would be super handy, but it causes the animation to play even before we click the switch, which is not right.

At this point [Will Boyd](http://codersblock.com/) stepped in with yet another bit of genius pure CSS trickery which you can view in the HTML and CSS tabs of the Airplane demo.

Will explained that by using the `:focus` pseudo selector and assigning a tabindex to the `<div>` containing the airplane, we are able to divert the browser from focusing on that animation until we click our toggle. Like I said, genius.

Here's a [handy article on styling toggles.](http://www.sitepoint.com/css3-toggle-switch/)

Happy toggled animating!
