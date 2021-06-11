***TInA*** is supplied as an self-contained [AppImage](bin/tina-x86_64.AppImage) (**Linux** equivalent of `.exe` on **Windows**).
It should be run in a `x86_64` **Ubuntu** *20.04* environment to work properly.

In addition to the *AppImage* itself, we released a **docker** container "ready-to-use".
*Container only wrap the content of the repository with the fixed dependencies.*

The setup will depend on the choosen method:

# Ubuntu 20.04 user

*AppImage* is working off-the-shelf.

# Docker user

In a terminal, use the following to install the container:
```shell
docker load < klee21-tina-artifact.tar.gz
```
Run the following to start an ephemeral (`--rm`) container:
```shell
docker run --rm -ti klee21-tina-artifact
```
The content of the repository is ready in the home directory.

#### Shared directory

It may be usefull to share files with the host system.
The additional argument `--mount` ([documentation](https://docs.docker.com/storage/bind-mounts/)) can help.
The following command will bind the current host directory (`$(pwd)`) to the docker `/shared` directory:
```shell
docker run --rm --mount type=bind,source="$(pwd)",target=/shared -ti klee21-tina-artifact
```