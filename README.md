# traefik_phantombot
### Phantombot with Traefik frontend, with self-signed SSL certificates
---
    https://containo.us/traefik/   
    https://phantombot.tv/    

#### Create passwd for Traefik Dashboard (`./traefik_users`)
**You'll need `htdigest` from `apache2-utils`**
1. `cd traefik_phantombot`
2. `htdigest -c traefik_users traefik admin`

#### Create Phantombot Environment File
```
MY_DOMAIN=mydomain.com
PHANTOMBOT_USER=twitch_username
PHANTOMBOT_OAUTH=oauth:someoauthtokenhere
PHANTOMBOT_APIOAUTH=oauth:anotheroauthtokenhere
PHANTOMBOT_CHANNEL=twitch_channel(if different from username)
PHANTOMBOT_PANELUSER=panel_user
PHANTOMBOT_PANELPASSWORD=panel_password
```
Save to ~/.phantombot_env, then create symbolic link:
1. `vi ~/.phantombot_env`
2. `chmod 0600 ~/.phantombot_env`
3. `ln -s ~/.phantombot_env /code/traefik_phantombot/.env`
