# chatGPT-discord-bot

> ### This is a project that provides you to build your own Discord bot using ChatGPT
>
> ⭐️ If this repo helps you, a star is the biggest support for me and also helps you stay up-to-date 
---
> **Warning**
>
> OpenAI added Cloudflare protections to their API in 2022-12-12, there are some differences in using it on server and desktop environment

## Features

* `/chat [message]` Chat with ChatGPT!
* `/private` ChatGPT switch to private mode
* `/public`  ChatGPT switch to public  mode
* `/reset`   ChatGPT conversation history will be erased

### Chat

### Mode

* `public mode (default)`  the bot directly reply on the channel
* `private mode` the bot's reply can only be seen by who use the command


# Setup

## Install

1. `pip install -r requirements.txt`

2. Run `playwright install` or `python -m playwright install`

## Step 1: Create a Discord bot

1. Go to https://discord.com/developers/applications create an application
2. Build a Discord bot under the application
3. Get the token from bot setting

4. **Change the file name of `config.dev.json` to `config.json`**
5. Store the token to `config.json` under the `discord_bot_token`

   
5. Turn MESSAGE CONTENT INTENT `ON`

   
6. Invite your bot to your server via OAuth2 URL Generator


## Desktop environments

> You do not need to fill out `session_token` in `config.json`

### Step 2: Run the bot
1. Open a terminal or command prompt
2. Navigate to the directory where you installed the ChatGPT Discord bot
3. Run `python3 main.py` to start the bot
### Step 3: log in
1. Wait for the Cloudflare checks to pass
2. Reload if show `ChatGPT is at capacity right now`
3. Log into OpenAI via the open browser (Your account)
4. It should automatically redirect you to https://chat.openai.com/chat after logging in. If it doesn't, go to this link manually after logging in.
5. The window should close automatically

### Have A Good Chat !

 
## Server & Docker

> You must fill the session token in `config.json`

### Step 2: Session token authentication

Go to https://chat.openai.com/chat log in

1. Open console with `F12`

2. Open `Application` tab > Cookies


3. Copy the value for `__Secure-next-auth.session-token` from cookies and paste it into `config.json` under `session_token`

### Step 3: Run the bot with docker

> I use `Xvfb` to emulate a desktop environment. It should automatically get the cf_clearance given no captcha

1. Build the Docker image `docker build -t chatgpt-discord-bot .`
2. Run the Docker container  `docker run -d chatgpt-discord-bot`

   ### Stop the bot:

   * `docker ps` to see the list of running services
   * `docker stop <BOT CONTAINER ID>` to stop the running bot

### Have A Good Chat !

## Optional: Setup starting prompt

* A starting prompt would be invoked when the bot is first started or reset
* You can set it up by modifying the content in `starting-prompt.txt`
* All the text in the file will be fired as a prompt to the bot  

---
