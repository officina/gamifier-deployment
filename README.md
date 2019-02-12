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
