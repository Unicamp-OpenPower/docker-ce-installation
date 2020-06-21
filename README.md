# Docker-CE Installation Script for PowerPC

Script to automate `docker-ce` installation on PowerPC for the versions available [here](https://oplab9.parqtec.unicamp.br/pub/ppc64el/docker/).

This script requires privileged access to the machine, it will also fetch/update the necessary depencies for `docker-ce`. It should also be noted that the depencies for `docker-ce` are not individually downloaded, instead the script will add repositories which contain the necessary dependencies, this method was chosen for simplicity.

The script was not tested on all operating systems for which it supports. Be cautious.

#### Supported Distros
* *Ubuntu*: bionic and xenial
* *Centos*: 7
* *Debian*: stretch
* *Rhel*: 7 (*not tested*)

## Depedencies

For the script itself, only `wget` and `git` are necessary.

As for `docker-ce` dependencies, the following items will be added:
* **Ubuntu** - The default repositories already contains all necessary packages.
* **Debian** - The packages [*libseccomp2*](http://ftp.us.debian.org/debian/pool/main/libs/libseccomp/), [*containerd*](http://ftp.us.debian.org/debian/pool/main/c/containerd/) and [*runc*](http://ftp.us.debian.org/debian/pool/main/r/runc/) will be added individualy.
* **Centos/Rhel** - The [EPEL](https://fedoraproject.org/wiki/EPEL) repository will be added, as it contains all necessary dependencies.

## Usage

Clone the repository and run the installation script provided. The distro will be identified automatically.

```
git clone https://github.com/Unicamp-OpenPower/docker-ce-installation
cd docker-ce-installation
sudo bash install_docker
```

If no versions are specified, the latest version available in the repository will be installed. To download a specific version, pass the version as an argument. 

```
sudo bash install_docker 19.03.0
```

you can list all the available versions with `-l`.

```
sudo bash install_docker -l
```

