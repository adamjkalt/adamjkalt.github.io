---
layout: post
title:      "CLI Data Gem Project"
date:       2018-05-31 13:45:52 -0400
permalink:  cli_data_gem_project
---


I recently finished up working on a fun CLI Application, looking at Upcoming Games being released for the Nintendo Switch.


![](https://www.nintendo.com/switch/etRgxnAu0zRX4bmWnt9K628wG7YQUI6t/images/switch/buy-now/bundle_gray_box.jpg)

CLI Application can be found here:

[](https://github.com/adamjkalt/Upcoming_Nintendo_Switch_Games_cli_app/tree/master/UpcomingNintendoSwitchGames)

As a long time fan of Nintendo, I thought this would be a fun project to work on.  

First, I had to just figure out where I would be scraping the data from, and realized metacritic would provide the information I'd need, in a straight forward manner.  

However, scraping the data from metacritic actually was a lot more complicated initially than I expected, as it wasn't as simple as just using Nokogiri to get the info that I needed.  Turns out that I need to install an additional gem to be able to scrape the page.  Through some searching on Google, I found another person who had scraped Metacritic and ran into the exact same issue.  

[](https://medium.com/@lukeghenco/my-first-ruby-gem-4e7ae3d8eda9)

Luke , in running to the exact same issue as I had, discovered that he needed to use OpenSSL to get the job done.  Being that he had already run into this issue, it was easy for me to just follow his lead.  Once the gem was installed, everything was working really well for the most apart, aside from tightening up some formatting issues in the CLI, which I did using regex.

The most complicated aspect for me, as being someone new to coding, was connecting the first level of scraping to the second level.  For the first level, scraping metacritic was very straight forward.  However, in the second level, I needed to make sure to interact with the user, to determine what game they wanted to learn more about, and then needed to scrape that specific page.  Early on, I included all the Game URL's in my scraping, but the initial challenge for me was figuring out how to connect the user's choice to the Game URL's I had found.

Here is what I ended up coming up with, which enabled everything to work as needed:

```
game_url = @games[input.to_i - 1][:url]
      the_game = Game.scrape_game(game_url)[0]
```

From here, I could then go in and access all the specific data from the game selected.

Overall, this project was a lot of fun, and a great first step in my coding journey.

