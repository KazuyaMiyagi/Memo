# Cron

## Install

### RHEL系

```
# yum install cronie
```

### Debian系

```
# apt-get install cron
```

## cron をフォアグラウンドで動かすオプション

### RHEL系

> -n     This option changes default behavior causing it to run crond in the foreground.  This can be useful when starting it out of init.

```
# /usr/sbin/crond -n
```

### Debian系

> -f      Stay in foreground mode, don't daemonize.

```
# /usr/sbin/cron -f
```
