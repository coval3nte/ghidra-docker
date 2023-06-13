# [Ghidra-Server](https://ghidra-sre.org/InstallationGuide.html) Plug&Play Docker

## Installation Steps
1. download and edit the [default config](https://github.com/NationalSecurityAgency/ghidra/blob/master/Ghidra/RuntimeScripts/Common/server/server.conf) parameters [1]
2. add _default_ (comma separated) users through the environment variable [default username\password: `admin:changeme`]
3. edit the [docker-compose.yml](docker-compose.yml) file (**expose** ports, **update version**, CI/CD magics ...)
4. `docker compose up -d`
5. Have Fun with your colleagues (or friends) and benefit of Collaborative Reverse Engineering

### Notes
> 1

* [!!!] `ghidra.repositories.dir=/repositories`
* `wrapper.app.parameter.*=...`, in order to meet your requirements (**ip** [2], ports, authentication mode ...)

> 2

It has to be the **origin** server's IP or Domain, otherwise pre-auth connection will fail automatically

> 3

Additional restrictions on access (IP based) could be added through mapping a config file to the container's path `/etc/nginx/stream-conf.d/access-list.conf`, following the nginx's __ngx_http_access_module__ rules

#### use at your own risk, find out more on official [ghidra website](https://ghidra-sre.org/)