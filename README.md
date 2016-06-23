# 5caaws
Five containers and a website

Getting this going on e.g. digital ocean requires the following steps:
1. starting a machine with the docker daemon
2. installing docker-compose: https://docs.docker.com/compose/install/
3. git clone https://github.com/pve/5caaws.git
4. restore the secrets from your stash
5. run docker-compose up
6. additionally, you might want to log the docker machine itself. i.e. https://XXXX.loggly.com/sources/setup/linux-setup-base


upgrading the underlying machine (not to mention the containers) can be done by just reinstalling on a fresh machine.
This will restore the backup.
