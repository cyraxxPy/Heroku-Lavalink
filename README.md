<h1 align="center">
  <br>
  Lavalink for Heroku
  <br>
</h1>

<h4 align="center">Modified lavalink for Heroku</h4>

<p align="center">
  </a>
  <a href="https://www.python.org/downloads/">
    <img src="https://img.shields.io/badge/Made%20With-Python%203.7-blue.svg?style=for-the-badge" alt="Made with Python 3.7">
    
  <a href="https://github.com/Rapptz/discord.py/">
      <img src="https://img.shields.io/badge/discord-py-blue.svg" alt="discord.py">
  </a>
<br>

# Deployment
[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/cyraxxop/Heroku-Lavalink)
### Easy way
* Click the button "Deploy to Heroku" above to install

### Alternative way
* Create an application on Heroku
* Add Java to buildpacks
* Fork this repo and deploy it to Heroku

# Features
* Uses **latest** release of Lavalink on (re)start
* Free to use
* Easy setup in ***3 clicks***

# Requirements
* Some knowledge of python
* Library to connect with Lavalink server [Lavalink.py](https://github.com/Devoxin/Lavalink.py) or [Wavelink.py](https://github.com/EvieePy/Wavelink) (you can also use other wrappers)
* Your time and mind!

# Notes:
* To run this 24/7, you need to make an account on [UptimeRobot service](uptimerobot.com/), and make HTTP request to your app every 5 minutes. For example, if your app is named `test-lavalink` then make HTTP request to `http://test-lavalink.herokuapp.com`

* Do not forget to edit config file (application.yml)
* Do not forget to set your password (`PASSWORD` environment variable)
* Do not change address and port in (application.yml)
* This repo means for students who cant pay and want to work or test lavalink. You might face music lags as heroku doesnt have high cpu specs.

# Connecting
* Lavalink's port will be always 80, DO NOT edit port in application.yml!
* Password is in `PASSWORD` environment variable, if variable does not exist, it is `youshallnotpass`

# Examples

## Python
### discord.py rewrite

* **Wavelink** | **[Repo Link](https://github.com/EvieePy/Wavelink)**
```python

    async def start_nodes(self):
        await self.bot.wait_until_ready()

        await self.bot.wavelink.initiate_node(host='test-lavalink.herokuapp.com',
                                              port=80,
                                              rest_uri='http://test-lavalink.herokuapp.com:80',
                                              password='youshallnotpass',
                                              identifier='MAIN',
                                              region='us')

        # ...
```
* **Lavalink.py** | **[Repo Link](https://github.com/Devoxin/Lavalink.py)**
```python
        if not hasattr(bot, 'lavalink'):  # This ensures the client isn't overwritten during cog reloads.
            bot.lavalink = lavalink.Client(bot.user.id)
            bot.lavalink.add_node('test-lavalink.herokuapp.com', 80, 'youshallnotpass', 'us', 'default-node')  # Host, Port, Password, Region, Name
            bot.add_listener(bot.lavalink.voice_update_handler, 'on_socket_response')

        bot.lavalink.add_event_hook(self.track_hook)

```
## Proper Examples:
* Lavalink.py - [Here](https://github.com/Devoxin/Lavalink.py/blob/master/examples/music.py) or [Here](https://github.com/Devoxin/Lavalink.py/blob/dev/examples/music.py)
* Wavelink.py - [Here](https://github.com/PythonistaGuild/Wavelink/blob/master/examples/basic.py)
# Advanced
### If you don't like default Heroku options for Java:
* You can set custom Java flags in `ADDITIONAL_JAVA_OPTIONS` variable. They **override** default config. **Do not** do this if you don't know what you're doing

## Credits
* [F4stZ4p](https://github.com/F4stZ4p/HLavalink)

### Contact
* [Join Discord](https://discord.gg/HKtQmtj)
* [Instagram](https://www.instagram.com/cyraxx_pubg)
* [Website](https://cyraxx.glitch.me)
