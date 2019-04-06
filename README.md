# AESBot
[![](https://img.shields.io/badge/License-GPL-blue.svg?logo=gnu)](https://github.com/iAmAsval/AESBot/blob/master/LICENSE)
[![](https://img.shields.io/badge/Twitter-@AsvalFN-1da1f2.svg?logo=twitter)](https://twitter.com/AsvalFN)
[![](https://img.shields.io/badge/Discord-Need%20Help%3F-7289da.svg?logo=discord)](https://discord.gg/JmWvXKb)

**A Discord bot to post Fortnite AES Keys built in Javascript and made for Heroku**

## GETTING STARTED
### Important
This bot is fully made for Heroku and isn't personalized at all. Read the code carefully to change/add some stuffs depending on your requirements (i.e. Heroku link to ping)
### Prerequisites
[Install Node.js](https://nodejs.org/en/)
### How does it works
**1.** Install all needed npm dependencies
```js
npm install axios
npm install discord.js
npm install express
npm install fortnite-api
npm install node-cron
```
**2.** Create your [Discord Bot](https://discordapp.com/developers/applications/)

**3.** Create your [Heroku App](https://dashboard.heroku.com/apps)
  - Go to `Settings`, `Add Buildpack` and select `NodeJS`
  - Go to `Settings`, `Reveal Config Vars` and add:
    - `aesCHANNELID` - the discord channel id where dynamic keys will be posted
    - `botPREFIX`
    - `botTOKEN`
    - `epicEMAIL` - [Fortnite-API](https://www.npmjs.com/package/fortnite-api) access_token used to ask the dynamic AES Keys
    - `epicPASSWORD` - [Fortnite-API](https://www.npmjs.com/package/fortnite-api) access_token used to ask the dynamic AES Keys
    - `sAESKEY` - the message posted when `aes` command is used
  - Go to `Deploy` and follow the steps depending on your deployment method

**4.** Open `AESBot.js`, change `http.get("http://aesbot.herokuapp.com/");` to `http.get("http://<your heroku app name here kthx>.herokuapp.com/");`
  
**5.** Your bot is now running 24/7 and is pinged each 5 minutes to keep it alive on heroku. Dynamic AES Keys are checked everyday at shop rotation time + 5 seconds, however if you wanna check if a key has been released early, use `faes`.
    
## DOCUMENTATION
### Features
1. `aes` - Post Fortnite Static AES Key
2. `faes` - Post Fortnite Dynamic AES Keys (Moderator role needed)
3. `clear amount` - Clear messages, default amount is set to 100 (User must have Manage Messages permission)
4. `help` - Summarize the commands
### What i'm using
- [Axios](https://www.npmjs.com/package/axios)
- [Discord.js](https://discord.js.org/#/)
- [Express](https://www.npmjs.com/package/express)
- [Fortnite-API](https://www.npmjs.com/package/fortnite-api)
- [node-cron](https://www.npmjs.com/package/node-cron)

## CHANGELOG
- 06/04/19 Initial Release v1.0

## TODO
- [ ] Better way to detect new keys, use this fucking txt file