---
layout: post
title: When Purchasing a Theme Is Not Enough
tags:
- WordPress
- HTML
- CSS
- PHP
featured_image: wordpress
link1_title: WordPress Theme Development
link1_url: https://www.sitepoint.com/premium/courses/wordpress-theme-development-2931/?ahref=icastillo
excerpt: As a developer, it is known that there are many ways to get websites up and running. There are thousands of themes to choose from when it comes to WordPress. For example, which one has the correct color, the correct plugin set, the correct styling that matches the brand we need, etc.
---
As a developer, it is known that there are many ways to get websites up and running. There are thousands of themes to choose from when it comes to WordPress. For example, which one has the correct color, the correct plugin set, the correct styling that matches the brand we need, etc. You then select the one that makes the most sense, install it, and alter it to the best of your ability. All is well.

Then comes the request for a change, a change that can be accomplished, that is with a bit of extra effort. From personal experience, I firmly believe you’ll have a smoother ride from your themes when they are customized and all options are made readily available within the admin area. This is great for people who do not want to mess with code, however this can prove to be a limitation for developers. The configurations can be buried deep in a config file or there is probably a framework on top of framework kind of deal. So then you find yourself wrestling with a theme wondering if life will ever be okay again. Of course I am speaking about a “friend of mine”.

So what do you do in this situation? Perhaps pursuing another career is probably out of the question! What I discovered in this situation is that I would often start with a purchased theme. Then changes were requested. Figuring out where those changes needed to be were often so time consuming. So I would then perform some sort of hacky thing to get it to function. After that, I found another hack was needed and yet another and another until I found myself slowly customizing every part of the site. It was no longer the same purchased theme. As you know it is probably better practice to do a child theme for this. Lightbulb moment: if I just created the theme from scratch I would know exactly where everything was at. I would be able to follow best practices, which is often something I discovered lacking on themes I had purchased.

The first thing you should know, when starting your own theme from scratch is that it helps to understand the template hierarchy of WordPress. The best place to read about that is here [Wordpress Template Hierarchy](https://developer.wordpress.org/themes/basics/template-hierarchy/). Once you have given that a good read you’ll begin to understand that it really doesn’t require that many files to get your theme off the ground. In fact, all you really need is the index.php file, the style.css and possibly the functions.php file. With these 3 files comes great power to rule the world, insert an evil laugh here.

You will slowly learn that if you take apart the latest theme, currently twentyseventeen, that comes installed from WordPress, it really is just broken apart into smaller pieces. In simple form, a theme is the header.php (top part), index.php (i call this the meat) and footer.php (the bottom part). If you start the theme creation process with just these items it makes the whole theming process easier. Sure there are loads of function calls, quarks and things you will have to learn along the way, but for the most part it is pretty straight forward.

In my course on SitePoint, [WordPress Theme Development](https://www.sitepoint.com/premium/courses/wordpress-theme-development-2931/?ahref=icastillo) you will see that I give instructions from an almost empty theme directory to theme for a site and blog area. Sometimes I feel like people make this too complicated and it can be easier once you understand the function calls; which files do what and how to pull it all together. I will say that after creating my own themes, it is difficult to revert back to a pre built one just because I know where everything is at and how it should load. So changes happen really quick and life becomes great again :).