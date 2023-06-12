# [Ghidra-Server](https://ghidra-sre.org/InstallationGuide.html) Plug&Play Docker

## Installation Steps
1. download and edit the [default config](https://github.com/NationalSecurityAgency/ghidra/blob/master/Ghidra/RuntimeScripts/Common/server/server.conf) parameters [1]
2. add _default_ (comma separated) users through the environment variable [default password: `changeme`]
3. edit the [docker-compose.yml](docker-compose.yml) file (expose ports, **update version**, CI/CD magics ...)
4. `docker compose up -d`
5. Have Fun with your colleagues (or friends) and benefit of Collaborative Reverse Engineering

### Notes
> 1

* [!!!] `ghidra.repositories.dir=/repositories`
* `wrapper.app.parameter.*=...`, in order to meet your requirements (ip, ports, authentication mode ...)

#### use at your own risk, find out more on official [ghidra website](https://ghidra-sre.org/)