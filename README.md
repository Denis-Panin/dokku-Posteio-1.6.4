
[![Poste.io](https://img.shields.io/badge/Poste.io-2.3.9-blue.svg)](https://poste.io/changelog)
[![Dokku](https://img.shields.io/badge/Dokku-Repo-blue.svg)](https://github.com/dokku/dokku)


# Poste.io plugin for Dokku (v1.6.4)

### What is Poste.io?

Poste.io is an full featured email server runing in a docker container. Read more at the [poste.io](https://poste.io/) website.

### What is Dokku?

[Dokku](http://dokku.viewdocs.io/dokku/) is the smallest PaaS implementation
you've ever seen - _Docker powered mini-Heroku_.

### Requirements
* A working [Dokku host](http://dokku.viewdocs.io/dokku/getting-started/installation/)

# Setup


## Download plugin
Log onto your Dokku Host to download and install plugin:
```bash
dokku plugin:install https://github.com/Denis-Panin/posteio
```
## PWD posteio in server
```bash
/var/lib/dokku/plugins/available/posteio
/var/lib/dokku/plugins/enabled/posteio
```

## Help
```bash
dokku posteio:help
```

## Domain name
Next setup domain name for posteio:

```bash
dokku posteio:set-domain mail.example.com
```

## Start container
To start using Poste.io you need to start his docker container:

``` bash
dokku posteio:start
```

**Note:**
You can disable features by passing these optional parameters to the start command:
- `--disable-clamav` to disable clamAV, it's useful to reduce memory usage if you don't need an antivirus protection.
- `--disable-rspamd` to disable Rspamd, it's useful to reduce memory usage if you don't want a spam filtering system.
- `--disable-roundcube` to disable the Roundcube webmail interface.

## SSL Certificate

Enabled SSL:
```bash
dokku posteio:toggle-ssl
```
