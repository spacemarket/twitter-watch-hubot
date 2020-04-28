# twitter-watch-hubot

Twitter watcher bot for slack.
This bot provides continuous watching specific keywords on Twitter, and output new result into Slack immediately.

Slack向けのTwitter監視botです。
Twitter上の特定のキーワードを監視し続け、結果を即座にSlackに出力します。


## Getting Started

### Heroku Button
[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

### Manual
1. `git clone git@github.com:spacemarket/twitter-watch-hubot.git && cd twitter-watch-hubot`
1. `npm install`
1. `heroku apps:create <app name>`
1. Set environment variables below (by `heroku config:add`).
1. Set up heroku addons.
  - `heroku addons:create redistogo`
  - `heroku addons:create scheduler:standard` ([more information](https://github.com/hubot-scripts/hubot-heroku-keepalive/tree/v1.0.0#waking-hubot-up))
1. `git push heroku master`

## Environment variables

- For [hubot-twitter-mention-v2](https://github.com/estiens/hubot-twitter-mention-v2)
  - `HUBOT_TWITTER_ACCESS_TOKEN_KEY`
  - `HUBOT_TWITTER_ACCESS_TOKEN_SECRET`
  - `HUBOT_TWITTER_CONSUMER_KEY`
  - `HUBOT_TWITTER_CONSUMER_SECRET`
  - `HUBOT_TWITTER_MENTION_QUERY` - Search keyword.
  - `HUBOT_TWITTER_MENTION_ROOM` - Channel name for bot's output(e.g. `random`)
- For [hubot-slack](https://github.com/slackhq/hubot-slack/tree/3.3.0)
  - `HUBOT_SLACK_TOKEN`
- For [hubot-heroku-keepalive](https://github.com/hubot-scripts/hubot-heroku-keepalive/tree/v1.0.0)
  - `TZ` - Time zone(e.g. `Asia/Tokyo`)
  - `HUBOT_HEROKU_KEEPALIVE_URL` - Endpoint to keepalive your bot.
  - `HUBOT_HEROKU_WAKEUP_TIME` - optional, the time of day (HH:MM) when hubot should wake up. Default: 6:00 (6 am) (for [hubot-heroku-keepalive](https://github.com/hubot-scripts/hubot-heroku-keepalive)).
  - `HUBOT_HEROKU_SLEEP_TIME` - optional, the time of day (HH:MM) when hubot should go to sleep. Default: 22:00 (10 pm)
  - `HUBOT_HEROKU_KEEPALIVE_INTERVAL` - the interval in which to keepalive, in minutes. Default: 5
