# gamifier-deployment
Repo containing the Playoff template configuration


To provide a simple way of configuring different deploy environment, there it is a config folder template.

In some files you can find some variable with a pattern like `{{VARIABLE}}`

The value of the variable is defined in the <env>_config.json file

where at the moment `env` can be, [dev] or [prod]

an example of json is this:

```
{
  "POSTGRES": {
    "USER": "user",
    "PASSWORD": "",
    "HOST": "",
    "PORT": "5432",
    "DB": "db"
  },
  "DISCOURSE_SECRET": "secret",
  "MAIL_SERVICE": {
    "NAME": "mail",
    "USERNAME": "username",
    "PASSWORD": "password"
  },
  "SSH_CONFIG_PATH": "/path/to/config/ssh_config",
  "SSH_USER": "ubuntu",
  "SSH_KEY_PATH": "/path/to/ssh/id_rsa",
  "ENV": "development",
  "PL_DOMAIN": "playoff.dev",
  "DOCKER_ENV": "vm",
  "MEMORY": {
    "GEARMAN": "64M",
    "REDIS": "128M",
    "HAPROXY": "64M"
  },
  "INSTALL_DIR": "/path/to/.pl"
}
```

an example of template file:

groups_var/all/base

```
env: {{ENV}}
docker_env: {{DOCKER_ENV}}
domain: {{PL_DOMAIN}}

iface: wlan0
force_https: false

alert_emails:
  - dev+revive@officina.cc

mmonit_host: {{MMONIT.HOST}}
mmonit_user: {{MMONIT.USER}}
mmonit_pass: {{MMONIT.PASSWORD}}


monit_runtime_user: {{MONIT.RUNTIME_USER}}
monit_user: {{MONIT.USER}}
monit_pass: {{MONIT.PASSWORD}}
monit_smtp_host: {{MONIT.SMTP_HOST}}
monit_smtp_port: {{MONIT.PORT}}
monit_smtp_username: {{MONIT.SMTP_USERNAME}}
monit_smtp_pass: {{MONIT.SMTP_PASSWORD}}


install_dir: "{{INSTALL_DIR}}"

docker_user: johny@playlyfe.com
docker_auth: am9obnk6QSFUQFIjbjRpNXY2

haproxy:
  check_interval: 5000

redis_host: {{REDIS_HOST}}

postgres:
  user: {{POSTGRES.USER}}
  password: {{POSTGRES.PASSWORD}}
  host: {{POSTGRES.HOST}}
  port: {{POSTGRES.PORT}}
  db: {{POSTGRES.DB}}
```
