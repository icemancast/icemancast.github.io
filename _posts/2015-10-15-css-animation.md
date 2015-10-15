---
layout: post
title: Getting Started with CSS Animation
tags:
- CSS
- Animation
- HTML
- Javascript
featured_image: css
link1_title: CSS Animation jsfiddle
link1_url: http://jsfiddle.net/icemancast/o1wj0cfx/4/
link2_title:
link2_url:
excerpt: I love animation ever since I was a kid. In the 3rd grade my brother and I would run home turn on the 3pm shows on TV and watch Tom & Jerry with our backpacks still on our backs.
---
I love animation ever since I was a kid. In the 3rd grade my brother and I would run home turn on the 3pm shows on TV and watch Tom & Jerry with our backpacks still on our backs. For some reason I have shied away from `CSS` animation. I did do animation the in the days of Macromedia Flash, yes before they were bought out by Adobe. I even picked up Real Media animation library for a quick month or so. Have you heard of that? Don't worry no one has. My next weapon of choice has been javascript and jquery and have never really looked back. I have seen some css animation come about and thought to myself oh that would be cool but never really thought explore more till just recently. Think of the animation in css as I need to setup a sequence that will happen at 0% time is zero and 100% is when the animation should finish at some "x" amount of time. Then in another class you would call that animation setup and actually set what time. This was probably the frustrating part for me when it came to css animation. I couldn't understand that the animation in `CSS` was a two part setup. Below is what a keyframe setup would look like:

    @keyframes whatever-name-i-choose {
        0% {
            opacity: 0;
            transform: translate3d(100%, 0, 0);
        }

        30% {
            opacity: 0.75;
        }

        100% {
            opacity: 1;
            transform: none;
        }
    }

The above `CSS` code will setup keyframes at 0%, 30% and the 100% mark of whatever time I set when I call this animation. You can set whatever percentages in the animation you would like by just doing a different percentage. Transform translate3d(x, y, z) will position the object all the way to the right offscreen and at the end of the animation we remove it by putting everything at 0. So the next question is how do we call this animation? Below is how I would call it in a class.

    .some-animation-name {
        animation-duration: 0.75s;
        transition-timing-function: ease-in;
        animation-fill-mode: both;
        animation-name: whatever-name-i-choose;
    }

The above will setup the class that needs to be animation while the @keyframes sets up the staged animation. Again took me a while to understand this was a 2 part setup which I believe kept me out of animation in `CSS` for a bit. You can see the fiddle below if you would like to mess around with the animation more. As always don't forget to read the documentation for this at: [CSS Animate Docs](http://www.w3schools.com/css/css3_animations.asp). Also if you would like below is a keyframe stage setup and the mixin I made for Sass so I could just extend it whenever I needed for that particular animated property.

    @keyframes position-from-right {
        0% {
            opacity: 0;
            transform: translate3d(100%, 0, 0);
        }

        30% {
            opacity: 0.75;
        }

        100% {
            opacity: 1;
            transform: none;
        }
    }

The mixin:

    /* @var $direction animation, @var $time of animation*/
    @mixin animate-property($direction: position-from-left, $time: 0.75s) {
        animation-duration: $time;
        transition-timing-function: ease-in;
        animation-fill-mode: both;
        animation-name: $direction;
    }

See the end product:

<iframe width="100%" height="300" src="//jsfiddle.net/icemancast/o1wj0cfx/4/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>