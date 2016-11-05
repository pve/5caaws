# 5caaws
## Five containers and a website

This restores a static website into Apache. A few risk management controls are implemented: backup/restore on AWS S3, logging on loggly.com 

Getting this going on e.g. Digital Ocean requires the following steps:

1. starting a machine with the Docker daemon (on Digital Ocean, take one of the one-click apps)
2. installing docker-compose: https://docs.docker.com/compose/install/ (you need a version 1.6 or better)
3. git clone https://github.com/pve/5caaws.git
4. restore the secrets from your stash
5. run docker-compose up
6. validate that you got the full restore, this can take a while; you are looking for the line that says "Job get finished" or "exited with code 0"
7. restrict the Docker machine login to two jumphosts
  *  /etc/hosts.deny sshd: All
  *  /etc/hosts.allow sshd: *your subnets*
8. additionally, you might want to log the docker machine itself. i.e. https://XXXX.loggly.com/sources/setup/linux-setup-base

Upgrading the underlying machine (not to mention the containers) can be done by just reinstalling on a fresh machine.
This will restore the backup.
