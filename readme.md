# Docker compose files to run Sonarqube, Jenkins and expose with Ngrok to the Internet

This repository contains docker-compose file to easily run to the code examples in the udemy courses

## Requirements
* Docker
* Docker compose
* ngrok account (Optional. Needed only if you want to expose the services in Internet)

## Switching SonarQube versions
You can check out other branches of the repository to launch other versions of SonarQube than that of the main branch. Check other branches available in the repository.

If you had a previous version and you want to modify it, I advise you to erase the volumes associated with the previous installation of docker compose.

# Ngrok configuration
* If you want to expose any of the services in Internet with ngrok, you'll need:
    * An [ngrok](https://ngrok.com/) account with an authentication token and a domain.
    * Create a .env file at the repo root folder to declare your ngrok domain and token 
```
NGROK_AUTHTOKEN=<your token>
NGROK_DOMAIN=<your domain>
```

# Launch modes
* Sonarqube: `docker-compose up`
* Sonarqube with postgres: `docker-compose -f compose.yaml -f compose.postgres.yaml up`
* Sonarqube + ngrok: `docker-compose --profile public up`

NOTE: You'll have a single domain with free ngrok account and you can only have a single ngrok session. So you can only expose either SonarQube or Jenkins at the same time
