# Installer Filebot avec Docker


## Prérequis
- Utiliser le container : `coppit/filebot` ou télécharger sur https://hub.docker.com/r/coppit/filebot


## Configuration
- Créer dossier /docker/filebot

Si besoin pour donner un accès

```shell
sudo chown -R 1042:1042 filebot
```

- Volumes
/media -> /media
/docker/filebot/config -> /config

- Ports
3389 -> 3389 (api)
8080 -> 8080 (ui)

## Editer fichier config
- Lancer une fois le container
- Stopper le container
- Editer `/docker/filebot/config/filebot.conf`
- Modifier `RUN_UI=no` en `RUN_UI=yes`
- Lancer le container
