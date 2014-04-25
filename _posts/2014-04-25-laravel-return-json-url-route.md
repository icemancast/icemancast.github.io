---
layout: post
title: Laravel Return Json From URL Route
tags:
- Laravel
- MVC Framework
featured_image: laravel
link1_title: Laravel Return Json Gist
link1_url: https://gist.github.com/icemancast/11293902
excerpt: I was asked what would be a good way to return json data from a url address. Doing some research and document reading I was able to
---
I was asked what would be a good way to return json data from a url address.
An example like visting url.com/posts.json would return acutal json data for
a mobile application. In rails this is already built in each controller which
is quite nice :). After doing some research and document reading I was able
to come up with the following easy solution in Laravel that I was very happy
with. Remember if you already have a post resource route place this json
route above that one for this to work. If you have solution that is different
than this one let me know, I would like this see it.

In your `routes.php` file place the following route or what makes sense for your situation.

    // Create route for json file
    Route::get('/posts.json', 'PostsController@postToJson');
    ...
    ...
    // Regular route resource if you have one
    Route::resource('posts', 'PostsController');

In your `postsController.php` file or any other controller add the following:

    // Create an action for the route
    public function postToJson()
    {
      // Query here for json you want to return
      $post = Post::all();

      // Send to json response
      return Response::json($post->toArray(), 200);
    }

Also below is a url to a gist of the code.

