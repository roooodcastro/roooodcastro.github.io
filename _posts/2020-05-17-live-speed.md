---
layout:        post
title:         "Live Speed - A Websockets Based Card Game"
thumbnail:     /images/posts/live-speed/logo.png
thumbnail_alt: "Project Logo - 2 playing cards with the text \"Live Speed\""
date:          2020-05-17 18:10:00 +0000
author:        Rodrigo Azevedo
categories:    projects
tags:
  - Web Development
  - Ruby on Rails
  - ActionCable
  - VueJS
---

<p class="d-none">
Implementation of a card game using Ruby on Rails, VueJS and websockets to allow for real-time, online gameplay.
</p>

<!--more-->

Live Speed is an implementation of the card game [Speed](https://en.wikipedia.org/wiki/Speed_(card_game)). Speed is a
fast-paced card game, played with a standard 52-card deck. The player's goal is to play their cards in order to get
rid of them before your opponent does. It's a game more heavily focused on speed and reflexes, and less on strategy.
Live Speed is meant to be played online with real people, but can also be played with an AI. It was developed using
the following stack:

* Ruby 2.6
* Rails 6.0 w/ Webpacker
* VueJS 2.5
* Websockets w/ ActionCable
* PostgreSQL
* Hosted on Heroku

Some helpful project links:

* [Project source code on GitHub](https://github.com/roooodcastro/live_speed)
* [Access and play Live Speed on Heroku](http://livespeed.rooood.com/)

### Motivation

The goal of this project was to serve as a sandbox to learn more and play with both ActionCable and VueJS. I had some
limited knowledge of Vue at the time, and wanted to expand on that. I also liked this specific game and played it a lot
with friends, and I figured its speed characteristic made it for a nice fit on a websockets project. Initially I had
the idea of finishing and polishing the game so it could actually be played and enjoyed by random people, but once it
became apparent that my inexperience with Vue made me take some bad decisions early on, I soon gave up on that.

### Implementation

The project is split into two main areas of development focus: the game itself, and the portal behind it. I started
with the game, which was mostly front-end work. I looked for and found some nice playing cards assets, and started
working out how to place, move and scale the cards on the board.

The "board" was simply a `<div>`, and each playing card was an absoluted positioned `<div>`. In hindsight, I
definitely should had used a `<canvas>` and a 2D graphics library, as it was a nightmare to figure out the positioning,
z-order, translations and transitions of the cards to make it look more like a game and less like HTML elements moving
around the screen. The cards were played via drag-and-drop action, and some care was taken to make the game scale and
respond to inputs decently on mobile.

The biggest challenge, and the reason I wish I had started using Vuex right from the start, was synchronizing the cards
after a player had played them. When Player 1 plays a card, ActionCable sent the action to the backend, which
processed it and broadcasted it back to all players. This triggered Vue to update the game board, refreshing and
re-creating the playing cards elements, and there are still bugs I couldn't solve around this.

{% include image.html name="game_ss.png" description="ScreenShot of the game board" %}

On the backend, the matches were modelled so each match have many rounds, allowing players to play "best of N" matches.
Each round had a status, which indicated whether the game had not started yet, was being played, paused, or finished.
When the match is created, or after a round is finished, a new round is created. This creation deals all cards and
stores the entire game state (each card on player's hands and piles, center piles, replacement piles) in a JSON
structure stored in a JSON column in PostgreSQL. This made the backend relatively simple to implement, as any update
on the round could be saved with just setting a JSON attribute and calling `round.save`, as ActiveModel magic already
took care of serialising and deserialising the data.

The game portal was to include features such as allowing people to play with or without accounts, allowing people with
accounts to access their match history and change some settings, and allowing all players to play matches of 2, 3 or 4
players, as well as having a match-making system that automatically connected two random players that were waiting for
matches. Some of these features are not yet implemented, such as settings, history, and 3 or 4 player matches.

All of the UI, UX and design including the logo was made by me (hence why it's not good), while I still had that idea
of having a polished game.

{% include image.html name="sign_up_ss.png" description="ScreenShot of the Sign Up page" %}

### Project status

I never fully finished the project, and probably never will. The game itself is essentially feature complete, with
only a few gameplay bugs that need squashing. The problem is that the website for the game required a lot more work
than I had anticipated, and implementing user/player registration, match finding/making/history, and all other things
that go with a game portal was not in line with my initial motivations.

Also, after I got more fluent in VueJS through work, I became aware that I should've used Vuex for this project. All
that kind of slowly chewed away my drive to finish the project, and so here it is, unfinished. Despite this, I've
learnt a lot about VueJS, ActionCable, websockets in general, and JS/CSS good practices throughout this project, so I'm
happy that I went as far as I did, and I feel it served its purpose.
