# Ubuntu base image for development environments

A Docker ubuntu image with some useful packages for development environments.
Do not use it for production.


## Installed softwares

 * vim
 * git + custom .gitconfig
 * zsh + oh-my-zsh + custom theme
 * curl
 * wget
 * unzip
 * telnet


## Non-root user and volume permissions

A `dev` user is created to perform non-root operations. The `dev` user does not have password and is sudoer.

To change the `dev` user UID / GID in Dockerfiles using this base image, use the `change-dev-id` command.

    RUN change-dev-id <NEWUID> [<NEWGID>]

If `NEWGID` is not specified, it will have the same value than `NEWUID`.

This command is useful to set the same permissions on files shared via a volume with the user on the host machine.
