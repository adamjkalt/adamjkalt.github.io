---
layout: post
title:      "Rendering and Redirecting with Sinatra"
date:       2018-08-31 21:47:43 +0000
permalink:  rendering_and_redirecting_with_sinatra
---


Rendering and Redirecting with Sinatra can be potentially confusing.  It's not necessarily difficult to figure out how to get your code working at all times, but while you may get things working, it's possible you may still not understand what is really happening when you Render as opposed to when you Redirect.

So, let's start with some basic concepts.

A Redirect creates a new HTTP Request.

However, an ERB/Render does not generate an http request.  This means that the browser isn't actually going anywhere different then where it is.

Rendering changes the content on the page in the existing route using the ERB File (from the Views)

```
  get '/games' do
    if logged_in?
    @user = current_user
    @games = @user.games
    erb :'/games/index'
  else
    redirect to '/login'
  end
  end
```

Another difference between the two, is that the argument to a Redirect is a route, while the argument to a Render is a file in the view folder.

As you can see from the above code, the ERB/Render provides the argument from the views folder (under game/index), while the argument in the Redirect is the route (/login).

Another very important thing to note is that the Redirect sends a new request and will lose all instance variables, so if you want access to those instance variables, you want to be Rendering.

So, if we need to take information from the Controller to the View, we need to use ERB/Render.

As you can see, there are plenty of differences between the two, but when initially learning about both, you may get caught up in simply trying to get your code to work/run, that you miss out on truly understanding the specific differences between them.
