<p align="center">
  <img src="https://telegra.ph/file/64a133a866ca17192f5dc.jpg">
<p>

<h1 align="center">
    GilbertAnimeBot
</h1>

<p align="center">
<a href="https://t.me/PegasusSupportOfficial"> <img src="https://img.shields.io/badge/Support-Chat-blue?&logo=telegram" alt="Support Chat" /> </a>
<a href="https://t.me/PigasusUpdates"> <img src="https://img.shields.io/badge/Update-Channel-blue?&logo=telegram" alt="Update Channel" /> </a><br>
<a href="https://t.me/GilbertAnimeBot"> <img src="https://img.shields.io/badge/GilbertAnimebot-blue?&logo=telegram" alt="Gilbert on Telegram" /> </a><br>
<a href="https://www.codefactor.io/repository/github/aasfcyberking/gilbertanimebot"><img src="https://www.codefactor.io/repository/github/aasfcyberking/gilbertanimebot/badge?s=f28e94dd3f2ef4ef858a0ad32b7c0519bfa11e48" alt="CodeFactor" /></a>
<a href="https://deepsource.io/gh/AASFCYBERKING/GilbertAnimeBot/?ref=repository-badge"><img src="https://static.deepsource.io/deepsource-badge-light-mini.svg" alt="DeepSource"></a><br>
<a href="https://python-telegram-bot.org"> <img src="https://img.shields.io/badge/PTB-13.5-brightgreen?&style=flat-round&logo=github" alt="Python Telegram Bot" /> </a>
<a href="https://github.com/psf/black"><img alt="Code style: black" src="https://img.shields.io/badge/code%20style-black-000000.svg"></a><br>
<a href="https://docs.telethon.dev"> <img src="https://img.shields.io/badge/Telethon-1.16.4-brightgreen?&style=flat-round&logo=github" alt="Telethon" /> </a>
<a href="https://docs.python.org"> <img src="https://img.shields.io/badge/Python-3.9.7-brightgreen?&style=flat-round&logo=python" alt="Python" /> </a><br>
<a href="https://github.com/AASFCYBERKING"> <img src="https://badges.frapsoft.com/os/v1/open-source.svg?v=103" alt="Open Source" /> </a>
<a href="https://GitHub.com/AASFCYBERKING/GilbertAnimeBot"> <img src="https://img.shields.io/badge/Maintained-Yes-brightgreen.svg" alt="Maintenance" /> </a><br>
<a href="https://github.com/AASFCYBERKING/GilbertAnimeBot/blob/main/LICENSE"> <img src="https://img.shields.io/badge/License-GPLv3-blue.svg" alt="License" /> </a>
<a href="https://makeapullrequest.com"> <img src="https://img.shields.io/badge/PRs-Welcome-blue.svg?style=flat-round" alt="PRs" /> </a>
</p>

<p align="center">
<a href="https://github.com/AASFCYBERKING/GilbertAnimeBot/fork">
    <img src="https://img.shields.io/github/forks/AASFCYBERKING/GilbertAnimeBot?label=Forks&style=social">
</a><br>
<a href="https://github.com/AASFCYBERKING/GilbertAnimeBot/stargazers">
    <img src="https://img.shields.io/github/stars/AASFCYBERKING/GilbertAnimeBot?label=Stars&style=social">
</a><br>
<a href="https://github.com/AASFCYBERKING/GilbertAnimeBot/issues">
    <img src="https://img.shields.io/github/issues/AASFCYBERKING/GilbertAnimeBot?label=Issues&style=social&logo=github">
</a><br>
<a href="https://github.com/AASFCYBERKING/GilbertAnimeBot/graphs/contributors">
    <img src="https://img.shields.io/github/contributors/AASFCYBERKING/GilbertAnimeBot?label=Contributors&style=social&logo=github">
</a><br>
<a href="https://github.com/AASFCYBERKING/GilbertAnimeBot/archive/refs/heads/main.zip">
    <img src="https://img.shields.io/github/repo-size/AASFCYBERKING/GilbertAnimeBot?label=Repo Size&style=social&logo=github">
</a>
</p>

**A modular Telegram Python bot running on python3 with a sqlalchemy, redis, telethon.**

## How to setup/deploy.

### Read these notes carefully before proceeding 
 - Your code must be open source and a link to your fork's repository must be there in the start reply of the bot.

<details>
  <summary>Steps to deploy on Heroku !!</summary>

```
Fill in all the details, Deploy!
Now go to https://dashboard.heroku.com/apps/(app-name)/resources ( Replace (app-name) with your app name )
REMEMBER: Turn on worker dyno (Don't worry It's free :D) & Webhook
Now send the bot /start, If it doesn't respond go to https://dashboard.heroku.com/apps/(app-name)/settings and remove webhook and port.
```

  [![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/AASFCYBERKING/GilbertAnimeBot.git)

</details>  
<details>
  <summary>Steps to self Host!! </summary>

  ## Setting up the bot (Read this before trying to use!):
Please make sure to use python3.6, as I cannot guarantee everything will work as expected on older Python versions!
This is because markdown parsing is done by iterating through a dict, which is ordered by default in 3.6.

  ### Configuration

There are two possible ways of configuring your bot: a config.py file, or ENV variables.

The preferred version is to use a `config.py` file, as it makes it easier to see all your settings grouped together.
This file should be placed in your `GilbertAnimeBot` folder, alongside the `__main__.py` file. 
This is where your bot token will be loaded from, as well as your database URI (if you're using a database), and most of
your other settings.

It is recommended to import sample_config and extend the Config class, as this will ensure your config contains all
defaults set in the sample_config, hence making it easier to upgrade.

An example `config.py` file could be:
```
from GilbertAnimeBot.sample_config import Config

class Development(Config):
    OWNER_ID = 2022280326  # your telegram ID
    OWNER_USERNAME = "AASFCYBERKING"  # your telegram username
    API_KEY = "your bot api key"  # your api key, as provided by the @botfather
    SQLALCHEMY_DATABASE_URI = 'postgresql://username:password@localhost:5432/database'  # sample db credentials
    JOIN_LOGGER = '-1234567890' # some group chat that your bot is a member of
    USE_JOIN_LOGGER = True
    DRAGONS = [1544286112, 1669178360]  # List of id's for users which have sudo access to the bot.
    LOAD = []
    NO_LOAD = ['translation']
```

If you can't have a config.py file (EG on Heroku), it is also possible to use environment variables. The following env
variables are supported:

- `ENV`: Setting this to ANYTHING will enable env variables

- `TOKEN`: Your bot token, as a string.
- `OWNER_ID`: An integer of consisting of your owner ID
- `OWNER_USERNAME`: Your username

- `DATABASE_URL`: Your database URL
- `MESSAGE_DUMP`: optional: a chat where your replied saved messages are stored, to stop people deleting their old
- `LOAD`: Space-separated list of modules you would like to load
- `NO_LOAD`: Space-separated list of modules you would like NOT to load
- `WEBHOOK`: Setting this to ANYTHING will enable webhooks when in env mode messages
- `URL`: The URL your webhook should connect to (only needed for webhook mode)

- `SUDO_USERS`: A space-separated list of user_ids which should be considered sudo users
- `DEV_USERS`: A space-separated list of user_ids which should be considered dev users
- `SUPPORT_USERS`: A space-separated list of user_ids which should be considered support users (can gban/ungban, nothing
  else)
- `WHITELIST_USERS`: A space-separated list of user_ids which should be considered whitelisted - they can't be banned.
- `DONATION_LINK`: Optional: link where you would like to receive donations.
- `CERT_PATH`: Path to your webhook certificate
- `PORT`: Port to use for your webhooks
- `DEL_CMDS`: Whether to delete commands from users which don't have rights to use that command
- `STRICT_GBAN`: Enforce gbans across new groups as well as old groups. When a gbanned user talks, he will be banned.
- `WORKERS`: Number of threads to use. 8 is the recommended (and default) amount, but your experience may vary.
  __Note__ that going crazy with more threads won't necessarily speed up your bot, given the large amount of sql data
  accesses, and the way python asynchronous calls work.
- `BAN_STICKER`: Which sticker to use when banning people.
- `ALLOW_EXCL`: Whether to allow using exclamation marks ! for commands as well as /.

### Python dependencies

Install the necessary Python dependencies by moving to the project directory and running:

`pip3 install -r requirements.txt`.

This will install all the necessary python packages.

### Database

If you wish to use a database-dependent module (eg: locks, notes, userinfo, users, filters, welcomes), you'll need to
have a database installed on your system. I use Postgres, so I recommend using it for optimal compatibility.

In the case of Postgres, this is how you would set up a database on a Debian/ubuntu system. Other distributions may
vary.

- install postgresql:

`sudo apt-get update && sudo apt-get install postgresql`

- change to the Postgres user:

`sudo su - postgres`

- create a new database user (change YOUR_USER appropriately):

`createuser -P -s -e YOUR_USER`

This will be followed by you need to input your password.

- create a new database table:

`createdb -O YOUR_USER YOUR_DB_NAME`

Change YOUR_USER and YOUR_DB_NAME appropriately.

- finally:

`psql YOUR_DB_NAME -h YOUR_HOST YOUR_USER`

This will allow you to connect to your database via your terminal. By default, YOUR_HOST should be 0.0.0.0:5432.

You should now be able to build your database URI. This will be:

`sqldbtype://username:pw@hostname:port/db_name`

Replace sqldbtype with whichever DB you're using (e.g. Postgres, MySQL, SQLite, `etc.)
repeat for your username, password, hostname (localhost?), port (5432?), and DB name.

Or, register on [ElephantSQL](https://www.elephantsql.com/) for free Postgresql. Learn for your self, I won't learn you
anything.
</details>

## Credits

- [Saitama](https://github.com/AnimeKaizoku/SaitamaRobot) This Bot Based On Saitama And For Anime Modules.
- [kurumi](https://github.com/Hirojazz/kurumi) For Some Modules 
- [Dank-del](https://github.com/Dank-del/Chizuru/) for some modules.
- [EverythingSuckz](https://t.me/EverythingSuckz) for NSFW filter and some other modules.
- [Hirojazz](https://github.com/Hirojazz) for Some modules.
- [Paul Larsen](https://github.com/PaulSonOfLars) Real Work.
- [Image-Editor](https://github.com/TroJanzHEX/Image-Editor) For ImageEditor Module
- [TroJanzHEX](https://github.com/TroJanzHEX) For ImageEditor Module
- [TheHamkerCat](https://t.me/TheHamkerCat) For Inline Features
## Warning⚠️

```
Fork At Your Own Risk 😸
Must Add The Orginal Repo Link On PM_START Else Gban And U Proving You itself Gay
```
