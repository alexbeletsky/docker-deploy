docker-deploy - deploy tool for remote docker server
====================================================

Install
-------

```
$ curl -O https://raw.github.com/nyarla/docker-deploy/master/docker-deploy 
$ chmod +x docker-deploy
```

Requirements
------------

  * `rsync`
  * `ssh`
  * `bash`

Help
----

```
docker-deploy - version 0.0.1

Usage: docker-deploy [options] <Dockerfile repository>

  Options:
    --build                     Building Dokerfile in remote docker server
    --deploy                    Deploying built Docker's container image
    --supervisor <system>       Specifying supervisor system (e.g. upstart)
    --tagprefix <`whoami`>      Prefix for Docker's -t option
    --sudo                      Using sudo when runnning remote command

    --user   <USERNAME>         Username for SSH
    --host   <ADDRESS>          Host address for SSH
    --port   <22>               Port number for SSH
    --sshkey <.ssh/id_rsa>      SSH pubic key

    -h, --help                  Show this ;-)
    -v, --version               Show version of this script
```

Usage
-----

### Building Dockerfile on remote server

```
$ docker-deploy --build --sudo \
	--user core \
	--host dev.sandbox.local \
	--tagprefix nyarla \
	/path/to/dockerfile/repository
```

### Deploying built container

```
$ docker-deploy --deploy --sudo \
	--user core \
	--host dev.sandbox.local \
	--tagprefix nyarla \
	--supervisor upstart
	/path/to/dockerfile/repository
```

Author
------

Naoki OKAMURA (Nyarla) *nyarla[ at ]thotep.net*

Unlicense
---------

`docker-deploy` is under the public domain.

