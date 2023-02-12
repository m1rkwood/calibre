# Calibre Web setup

This docker will setup Calibre-Web on your server.
You need to have an existing Calibre database. You can generate it with the desktop application.
You will need to upload your library to the server (although it also works with Google Drive)
To use this configuration, you will have to also run the `traefik-docker` project available [here](https://github.com/m1rkwood/traefik-docker).

## Folder structure

```
.env
docker-compose.yml
```

## Envionment

Duplicate the `.env.template` file and rename it to `.env`
Fill the information:

```
TZ=
VIRTUAL_HOST=
PATH_TO_LIBRARY=
PUID=
PGID=
```

`TZ` is your timezone, i.e. `America/Los Angeles`.
`VIRTUAL_HOST` is the complete url (with subdomain) where the app will appear.
`PATH_TO_LIBRARY` is the relative path to your books on the server.

To find `PUID` and `PGID`, go `id username`, `username` being the owner of the books library on the server. You can find the name of the owner of the library by doing ls -la <PATH_TO_CALIBRE_LIBRARY>
