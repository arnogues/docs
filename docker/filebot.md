# Installer Filebot avec Docker


## Prérequis
- Utiliser le container : `jlesage/filebot` ou télécharger sur https://hub.docker.com/r/jlesage/filebot


## Configuration
- Créer dossier /docker/filebot

Si besoin pour donner un accès

```shell
sudo chown -R 1042:1042 filebot
```

- Volumes
- /media -> /media
- /docker/filebot/config -> /config

- Ports
5800 -> 5800

## Editer fichier config
- Lancer une fois le container
- Stopper le container
- Editer `/docker/filebot/config/filebot.conf`
- Modifier `RUN_UI=no` en `RUN_UI=yes`
- Lancer le container
