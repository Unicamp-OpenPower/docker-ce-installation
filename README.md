# Docker-CE Installation Script for PowerPC

Script to automate `docker-ce` installation on PowerPC for the versions available [here](https://oplab9.parqtec.unicamp.br/pub/ppc64el/docker/).

This script requires privileged access to the machine, it will also fetch/update the necessary depencies for `docker-ce`. It should also be noted that the depencies for `docker-ce` are not individually downloaded, instead the script will add repositories which contain the necessary dependencies, this method was chosen for simplicity.

The script was not tested on all operating systems for which it supports. Be cautious.

## Depedencies

For the script itself, only `wget` and `git` are necessary.

For `docker-ce`, the following items will be added:
* **Ubuntu** - The default repositories already contains all necessary packages.
* **Debian** - The packages *libseccomp2* and *containerd* will be added individualy.
* **Centos** - The [EPEL](https://fedoraproject.org/wiki/EPEL) repository will be added, as it contains all necessary dependencies.

## Usage


