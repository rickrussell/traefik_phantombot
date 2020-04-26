# traefik_phantombot
Phantombot with Traefik frontend, with self-signed SSL certificates

## Create passwd for Traefik Dashboard and drop into `./traefik_users`
** You'll need `htdigest` from `apache2-utils`
`cd traefik_phantombot`
`htdigest -c traefik_users traefik admin`

## Create Phantombot Environment File
```
MY_DOMAIN="mydomain.com"
PHANTOMBOT_USER=twitch_username
PHANTOMBOT_OAUTH_TOKEN=oauth:someoauthtokenhere
PHANTOMBOT_APIOAUTH=oauth:anotheroauthtokenhere
PHANTOMBOT_CHANNEL=twitch_channel(if different from username)
PHANTOMBOT_PANEL_USER=panel_user
PHANTOMBOT_PANEL_PASSWD=panel_password
```
I save mine to ~/.phantombot_env, `chmod 0600 ~/.phantombot_env` then create symbolic link:
`ln -s ~/.phantombot_env /code/traefik_phantombot/.phantombot_env`
