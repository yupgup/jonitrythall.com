---
layout: post
title: Sass FUNction Demos
date: '2017-01-26 15:07:48'

# Legacy
redirect_from:
    /sass-function-demos/
---

![Preview of three Sass demos](/content/2017/01/preview.png)

I’ve been looking for mini mental distractions from our current political emergency a lot lately, which I have found through Sass and animations. Sass is incredibly powerful and I still find myself in awe of its potential. I set out to have fun with some areas that I don’t use much in my current day-to-day work tasks.

I ended up putting a few rage fueled demos together that use different list and color functions. This post serves as a brief walk through of the bits of Sass that made each especially enjoyable and distracting to create.  

## Animated Demos
The foundation of these four animated demos are color lists and the `random()`, `nth()`, and `mix()` functions. There are also a few `@for` directives to help loop through several elements and assign values.

### `random()` Rage Confetti

<p data-height="300" data-theme-id="11708" data-slug-hash="jywwMY" data-default-tab="result" data-user="jonitrythall" data-embed-version="2" data-pen-title="random() Rage Confetti " class="codepen">See the Pen <a href="http://codepen.io/jonitrythall/pen/jywwMY/">random() Rage Confetti </a> by Joni Trythall  (<a href="http://codepen.io/jonitrythall">@jonitrythall</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

The primary magic here comes from randomly placing dots on the screen, randomly animating and delaying their movement, and randomly assigning and changing their colors between two lists.  

#### `random()`
The `random()` function can return a random value within a single limit (including 1 and the limit itself) or a random value within a range. So while `top: random(340) + px;` will produce a random pixel value from 1 to 340, a value of something like `right: random(400) + 200 + px;` will produce a random pixel value between 200 and 600.

For a negative value here something like `right: random(200) - 100 + px;` will move right along a range of -100 to 100 pixels.

The animation value below will move a dot along the x axis to a random point up to `1100px`.

    transform: translateX(random(1100) + px)

*I also relied heavily on `random()` to [replicate the new Ela Conf pattern](http://codepen.io/jonitrythall/pen/QdKZBz) recently*.

#### `@for`
The `@for` directive allows for each of the 150 dots to be looped through, applying the randomly set styling to each one.

    $num: 150;
    @for $i from 1 through $num {
      .dot:nth-of-type(#{$i}) {
          // Where are the declarations live
      }
    }

The `$i` variable serves as an incremental placeholder for 1 through 150, the counter.

#### `@if`
The `@if` control directive is handy in specifying that half of the dots should have an animation delay, otherwise they all move at once and it’s much less exciting.

    $num: 150;
    $some: random($num);
    @if $some > ($num / 2) {
      animation-delay: random(3000) + ms;
    }

The `$num` variable simply reflects the number of dots that are being generated via HTML and `$some` houses a random number from this number (1-150 dots). **If** the random number is greater than 75 (`$num / 2`) then the `animation-delay` will be applied. Writing it this way permits the continued ability to experiment with these values.

### Unite `nth()` Loader

<p data-height="300" data-theme-id="11708" data-slug-hash="JEJxGO" data-default-tab="result" data-user="jonitrythall" data-embed-version="2" data-pen-title="Unite Loader " class="codepen">See the Pen <a href="http://codepen.io/jonitrythall/pen/JEJxGO/">Unite Loader </a> by Joni Trythall  (<a href="http://codepen.io/jonitrythall">@jonitrythall</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

There are five squares in this demo that visually transition into a single dot. The `nth()` list function is used to select certain colors within the `$colors` list to apply to each object.

    nth($list, $n)

`nth()` accepts two parameters: the name of the list and the index of the item within that list.

Here is a look at the code to apply the third color to the third object:

    // List of colors
    $colors: #ADD3C9, #EA758C, #FBFBFB, #26356E, #721840;

    // Color assignment
    .dot:nth-child(3) {
        background: nth($colors, 3);
    }

The color of the third `.dot` becomes `#FBFBFB`, the third color in the list.

Through a series of five slightly different animations the dots are moved to the center with appropriate `translateX` and `translateY` values.

### Color `mix()` Bubbles
This demo randomly positions and moves bubbles through `@for` loops and `random()`, as seen in the confetti demo. However, it also utilizes a Sass color function when generating a background color (`mix()`).

#### `mix()` Color Function

<p data-height="300" data-theme-id="11708" data-slug-hash="OWjLGV" data-default-tab="result" data-user="jonitrythall" data-embed-version="2" data-pen-title="Color mix() Bubbles" class="codepen">See the Pen <a href="http://codepen.io/jonitrythall/pen/OWjLGV/">Color mix() Bubbles</a> by Joni Trythall  (<a href="http://codepen.io/jonitrythall">@jonitrythall</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

The `mix()` function [allows two colors to be mixed](http://sass-lang.com/documentation/Sass/Script/Functions.html#mix-instance_method) to generate a third output color by accepting three parameters:  

    mix($color1, $color2, [$weight])

Two colors are accepted while setting a percentage based weight defines how much of the first color should be included within the returned generated color. A `weight` value of `80%` here would mean that `80%` of the first color and `20%` of the second color are used.  

In order to randomly mix the colors, and not include single hex values as shown in the snippet above, `mix()` and `random()` must both be utilized.

    // List of colors    
    $colors: #A32D70, #6E32A0, #DBD3D9, #D64369, #7A7DE0;

    // Background of bubbles
    background: mix(nth($colors, random(length($colors))), nth($colors, random(length($colors))), 60%);

The code above mixes one random color within another random color, both or which are determined from the list of colors within the `$colors` variable. The percentage value states that the generated color will consist of `60%` of the first random color that is selected.  

#### `desaturate()` Color Function
At the `50%` moment within the `@keyframes` animation the background is set to change to desaturated version of another random color.

    50% {
      background: desaturate(nth($colors, random(length($colors))), 50%);
    }

The `desaturate()` function decreases the saturation of the bubbles, making them transition into a paler appearance through the `float` animation.

*There are loads more of these beautiful [color functions](http://sass-lang.com/documentation/Sass/Script/Functions.html) worth checking out*.

### Loopy Line Loader

<p data-height="300" data-theme-id="11708" data-slug-hash="ffacffea62e68c18a603ae1699f32641" data-default-tab="result" data-user="jonitrythall" data-embed-version="2" data-pen-title="Loopy Lines Loader" class="codepen">See the Pen <a href="http://codepen.io/jonitrythall/pen/ffacffea62e68c18a603ae1699f32641/">Loopy Lines Loader</a> by Joni Trythall  (<a href="http://codepen.io/jonitrythall">@jonitrythall</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>

This demo utilizes the `@for` directive to loop through all fifteen lines and individually apply styling and an animation to each. The `background` color is set to cycle through a list of colors in the `$colors` variable via an `@if` control directive, adding 1 to the list index each cycle of the loop.

The `@keyframes` multiplies movement to the right on each line count to ensure even spacing:

    @for $i from 1 through 15 {
      .line:nth-of-type(#{$i}) {
        animation: stack#{$i} $dur;
      }

      @keyframes stack#{$i} {
        50% {
          transform: translateX(-($right * $i)) $turn;     
        }
      }
    }

### End
There is so much fun programming to be had without ever having to leave a `.scss` file. Since I find rage to be the most significant motivator I suspect I will be publishing more of these soon if you’d like to [follow along](http://codepen.io/jonitrythall/).

*I considered writing out a weird `@each` directive here to thank each of you for reading but am embarrassed I even considered this.*
