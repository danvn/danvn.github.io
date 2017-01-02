---
layout: post
title: "Recaptain"
date: 2016-11-09
excerpt: "Summer 2016 Internship for ReadyTalk, Denver (LoDo)"
project: true
tag:
- internship
- software
- machine_learning
- NLP
- Watson
- Docker
- Slack
- Bot
- AI
- Readytalk
comments: true
---

# Recaptain
ReadyTalk Intern Project Summer 2016

Recaptain is a bot build for Slack, a cloud-based team collaboration software tool. Recaptain is used to summarize the chat log in a public channel in the team. A user would install the Recaptain bot, then message Recaptain to request a summary of a desired chanel. Recaptain will respond with key messages from the conversation that are marked at a higher importance. A message becomes important from a message analyzer library called Watson. 


The Recaptain Slack Bot made for ReadyTalk Summer 2016 was the largest project I've contributed to and I feel I made a large impact.

4 of us interns were sought out to provide solutions to the problem of "Too much chat, not enough time". This problem was a reference to the amount of non-work-related messages on Slack. 

The full blog of the project can be found at http://dannguyen.me//recaptain/

To understand the problem we looked through our teams channels and chat logs. We understood that people don't want to be sent memes or gifs when they are trying to be productive.

The Recaptain Bot used IBM Watson NLP API to determine which messages were important. I contributed a message scoring system that made calls to Slack to retrieve messages and return to the user daily "Recap" of the channel.

I constructed the methods used to talk to Slack and respond to the user as per request. The response to the user was a "Recap" of the most important messages from the channel in a given time range, ignoring the fluff of giphy memes and images, and only delivering the "important" messages, as deemed by our NLP library. 


## Installation

## Requirements:
node v6.2.2

Generate a unique token for the bot on 
	<a href="https://team_name.slack.com/apps/build/custom-integration">slack: </a>

	Bots -> Bot Username -> Add Bot Integration
	Copy the API Token from the Integration settings 

## Running
from root dir, run

`token=... node app.js`
	<b>OR</b>
`token=... npm start`

## Docker

One of the goals for the project was to ship the software public so that any company or Slack team would be able to use Recaptain. 
I learned about Docker which is a solution to software dependencies and inconsistencies in the form of containers. 

In the way that Virtual Machines separate operating systems from the underlying hardware that they run on,

Docker separates applications from the underlying operating systems that they run on.

When deploying software with a Virtual Machine, an application consists of a the application code, bins/libraries, and a heavy "Guest OS". The Guest OS can be heavy and decrease portability and causes trouble in terms of tying the application to the OS.

Docker <i>virtualizes</i> the OS. Only our application and its dependencies are contained which makes our application extremely fast and portable, and we don't have the operating system to worry about; it is outside of our container. We can deploy these containers virtually anywhere (desktops / laptops / virtual machines / clouds). They also have very flexible scalability. 

Developers can build in any language, any environment, with any tools. 

Dockerized applications can run anywhere and on anything, so we don't have to worry about anything when porting or deploying our applications.

Docker fights against "Dependency Hell", uniting devlopers and system administrators.

In practice, we will have a base <b>image</b> layer that contains our environment and application (node on ubuntu, for us in this example). When we are ready to update a new image layer, to update, one must only simply download the new layer which are only the new changes; not the whole image again.

Then we move to <b>containers</b>, where we essentially turn those images "on". We then spin up a new container, specifiying an image, and we have a live environment and application running in our <i>isolated</i> container. We can <i>start, stop, move, and delete</i> containers. 

```
docker build -f Dockerfile-prod -t "recapitan-prod" .
docker run recapitan-prod --env=TOKEN=....
```

## Usage
Once Recaptain is in the slack team, simple 'Direct Message' the bot.
The avaliable commands are
{% highlight yaml %}
hi
help
recap
recap #channel_name1 #channel_name2 ...
{% endhighlight %}

### The help command is the easiest way to get started
It will give you a tutorial to use the bot with a bunch of helful parameters to get you the summary you want.
