---
layout: post
title:      "Video Game Library"
date:       2018-08-14 03:21:53 +0000
permalink:  video_game_library
---


![](http://www.mobygames.com/images/covers/l/13521-the-legend-of-zelda-a-link-to-the-past-snes-front-cover.jpg)

I am in the process of finishing up my Sinatra Portfolio Project.  Working on independent projects has been something I have enjoyed a lot, as it has been very cool to have a concept, and then be able to make it a reality.

As the assignment was to build a CRUD App (Create, Read, Update, Delete), I decided to stay in the same category of my CLI Gem Project (video games), and this time built a Video Game Library/Organizer.

The Application allows users to organize their Game Libraries in very simple fashion.

The User first must sign up for an account (Username, Email, and Password), and at that point has the ability to create their video game library.  

The first step is for the user to Add Games and either Add a Console at that point, or just identify which Console the game belongs to.

Once a Game and a Console have been created, the User can View their Games, Edit any of their Games, as well as View their Consoles and see which games are for which consoles.  Navigation is pretty straight forward.

I still need to go in and create my Delete function, as well as make sure that Users make sure to enter specific data (i.e. don't add a game without adding a console, or vice versa).

So far, the biggest challenge was making sure that Specific Games/Consoles belonged to a User.  Originally, all Games and Consoles were just showing up, regardless of who was logged in.  

There were two steps that were needed to fix this issue.

The first step was by updating the tables and adding user_id to both the games and consoles tables:

```
class CreateConsoles < ActiveRecord::Migration
  def change
    create_table :consoles do |t|
      t.string :name
      t.integer :user_id
    end
  end
end
```

```
class CreateGames < ActiveRecord::Migration
  def change
    create_table :games do |t|
      t.string :name
      t.integer :console_id
      t.integer :user_id
    end
  end
end
```

The second step was by making sure to give the game/console to a specific user when the game/console were being created.

```
  post '/games' do
  @game = Game.create(name: params["Name"])
  @game.console = Console.find_or_create_by(name: params["Console Name"])
  @game.save
  current_user.games << @game
  current_user.consoles << @game.console
  redirect("/games/#{@game.slug}")
  end
```

Once this was done, the Users now had their specific games/consoles.  

Overall, this has been a really enjoyable project, and I look forward to learning more, and working on the next one!
