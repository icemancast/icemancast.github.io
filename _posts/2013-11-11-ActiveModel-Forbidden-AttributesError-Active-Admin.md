---
layout: post
title: How to Fix ActiveModel::ForbiddenAttributesError with ActiveAdmin
tags:
- Rails 4
featured_image: rails
link1_title: Strong Parameters Explained
link1_url: http://guides.rubyonrails.org/action_controller_overview.html#strong-parameters
link2_title: Fix for Active Admin
link2_url: http://stackoverflow.com/questions/13091011/how-to-get-activeadmin-to-work-with-strong-parameters
excerpt: I came across an error on a rails project I am working on, ActiveModel::ForbiddenAttributesError. Of course right away I hit up google to find an answer
---
I came across an error on a rails project I am working on,
ActiveModel::ForbiddenAttributesError. 
Of course right away I hit up google to find an answer.
Found out that there was a change from Rails 3 to Rails 4 please read
the Strong Parameters Explained in the documentation below. After
attempting their suggestions it still did not work for me till I found
the article at stack overflow, which will soon be your go to if you
begin programming. I was attempting the fix correctly but because it has
Admin Admin you need to do that change in the admin controller. If you
are not using Active Admin then just use the suggestions per the Rails
Guide Docs.
