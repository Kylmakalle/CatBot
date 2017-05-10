# CatBot Telegarm Bot

Telegram Bot that sends you cat gifs from [TheCatApi.com](https://thecatapi.com/) 

[@Cats4FunBot](https://t.me/Cats4funbot)

## Installation

### Quick Start for Ubuntu 16.04
```
# install git and python3
sudo apt update
sudo apt install git python3 python3-dev python3-pip
# clone repository
git clone https://github.com/Kylmakalle/CatBot.git
cd CatBot
# update python pip and install module requirements
sudo -H pip3 install -U pip setuptools wheel
sudo -H pip3 install -r requirements.txt
cp set_env.example.sh set_env.sh
```
- Create new Telegram bot with any name by sending `/newbot` command to [@BotFather](http://telegram.me/botfather) and copy token to access the HTTP API to `set_env.sh`
- Add **/cat** command to the bot using **/setcommands** or inline buttons: `cat - get CatGif`

#### Run
```
chmod +x run.sh
./run.sh
```

#### Update
```
git pull
sudo -H pip3 install -r requirements.txt
```

## Deploying to [Heroku](https://heroku.com/)

Install [Heroku Toolbelt](https://toolbelt.heroku.com/), then:

```
cd Catbot
heroku login
heroku create catbot # create app (may not be available, try your own)
heroku buildpacks:set heroku/python # set python buildpack
git push heroku master # deploy app to heroku
heroku config:set TELEGRAM_TOKEN=123456789:AAABBBCCCDDDEEEFFFGGGHHHIIIJJJKKKLL # set config vars, insert your own
heroku ps:scale bot=1 # start 1 bot dyno
heroku ps:stop bot # or stop bot dyno
```

- https://devcenter.heroku.com/articles/dynos
- https://devcenter.heroku.com/articles/config-vars
