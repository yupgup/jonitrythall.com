---
layout: post
title: jQuery Snippet Heavy Hitters
date: '2015-01-26 13:47:48'

# Legacy
redirect_from:
    /blog/blog/jquery-snippet-heavy-hitters/
---

![Illustration of boxing gloves depicting a match between .toggleclass and .preventDefault](/content/2015/Jan/boxingintro.jpg)

As with almost all things in this field that initially approach, JavaScript was (is) really intimidating. Now, I'm certainly not saying that I am some sort of expert now, but I am in deep enough at this point to detect that a large portion of what I need JavaScript for in the front-end world can be done with one of a few snippets of jQuery it seems.

[jQuery](http://jquery.com/) is an amazingly powerful JavaScript library that makes DOM manipulation and event handling much more straightforward over "full blown" JavaScript.

Anyone new to front end development will fairly quickly realize the limitations of HTML and CSS concerning things like interactivity, for example, or using CSS to achieve a certain effect would simply go against best practices.

Either way, it can be pretty overwhelming. You just got somewhat comfortable with HTML/CSS (you know, as much as anyone can be with these things) and now you have to learn programming?! Hopefully reviewing some commonly used jQuery snippets and use case examples will help eliminate any lose of sleep.

This post will refer to the following demo throughout:

<p data-height="427" data-theme-id="11708" data-slug-hash="2f3ee2e5daf6a4a75cc069b444c37d81" data-default-tab="result" data-user="jonitrythall" class='codepen'>See the Pen <a href='http://codepen.io/jonitrythall/pen/2f3ee2e5daf6a4a75cc069b444c37d81/'>2f3ee2e5daf6a4a75cc069b444c37d81</a> by Joni Trythall  (<a href='http://codepen.io/jonitrythall'>@jonitrythall</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

*[View full demo on CodePen](http://codepen.io/jonitrythall/pen/2f3ee2e5daf6a4a75cc069b444c37d81)*

### Hide Broken Images
If you look in the HTML of the demo we will be referencing for this post, there is a broken <code>img</code> tag in the header. The following bit of jQuery hides broken images on the page, sparing us from having to look at that ugly broken image icon.

	// Hide broken images!
	$("img").error(function(){
        $(this).hide();
	});

Otherwise this guy would be hanging out right at the top of the page:

![screenshot of broken image icon](/content/2015/Jan/Screen-Shot-2015-01-21-at-12-46-11-PM.png)

### Show & Hide
To show and hide something on click we can use <code>.toggle()</code>.

The sign up button in the demo toggles the sign up form that is hiding at page load.

	$(".form-title").click(function() {
  	$(".signup-form").toggle();
	});

<code>.form-title</code> represents the sign up button, which on click toggles <code>.signup-form</code>.

### Cycle Through List
This is perhaps the most fun snippet on the list. This [bit of jQuery I grabbed from CSS-Tricks](http://css-tricks.com/snippets/jquery/cycle-through-a-list/) cycles through the boxing benefits <code>ul</code> in our demo, displaying one at a time.

To make this work be sure to add an <code>id</code> of "cyclelist" to the <code>ul</code>.

	$(document).ready(function() {

	 	var j = 0;
	 	var delay = 2000;
	 	function cycleThru(){
        	var jmax = $("ul#cyclelist li").length -1;
        	$("ul#cyclelist li:eq(" + j + ")")
        	.animate({"opacity" : "1"}, 400)
        	.animate({"opacity" : "1"}, delay)
        	.animate({"opacity" : "0"}, 400, function(){ (j == jmax) ? j=0 : j++;
       			cycleThru();
     		});
   	   };

	 	cycleThru();

 	});

You will also want to have <code>opacity: 0;</code> in your CSS for the list items to avoid a big ugly mess! Also note that there is the inclusion of opacity animations to smooth out the list transition.

### Setting an Active Class & Toggling
This is my favorite snippet and perhaps the one I use the most at this point. As designers and developers we are constantly having to tell something to do something once something happens. It's a really bossy job and active classes help us fine-tune all these interactions.

At the bottom of our boxing demo there is an input to sign up for a newsletter. Once the submit button is clicked the input field turns green. The following snippet adds a class to the input, which is where the background change is declared.

	$('.get-newsletter').on('click', function(evt) {
 	 	// prevent default actions
 		 evt.preventDefault();

  		$('.news-input').toggleClass('is-active');

	});

To make this work for you grab the button, a class of <code>get-newsletter</code> here, specify where you would like the class appended (<code>.news-input</code> in the demo) and then declare your styling for this active class.

	.news-input.is-active {
  		background: #41c44e;
	}

The <code>preventDefault</code> bit ensures that this form does not actually submit anything and we don't see prompts like the one shown below when using the demo:

![Screenshot of prompt that dispays without having preventDault in your JavaScript](/content/2015/Jan/Screen-Shot-2015-01-25-at-7-45-46-PM.png)

You can also [add and remove classes on hover](http://css-tricks.com/snippets/jquery/addingremoving-class-on-hover/).

### Knock Out
So while there is [*a lot*](http://learn.jquery.com/using-jquery-core/) more you can do with jQuery (Animations! Storing data! Equal div sizing!), these are examples of what I find myself running into regularly with front-end work. Through these specific scenarios we can help fill in the gap left in our projects after we have our HTML and CSS in place, adding to the usability, functionality, and overall experience of the site.  

For further reading reguarding common jQuery snippets, I found [this article by Sara Vieira](http://www.webdesignerdepot.com/2014/01/10-jquery-snippets-every-designer-should-know/) and the [jQuery snippets page over at CSS-Tricks](http://css-tricks.com/snippets/jquery/) to be handy resources.
