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

## Production Docker

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
