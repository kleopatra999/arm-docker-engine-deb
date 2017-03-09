# armhf-docker-engine-deb

This is a short documentation how to build the docker-engine Raspbian package for ARM from master branch.
Its purpose is to test the fix for https://github.com/docker/docker/issues/30590 on a Raspberry Pi Docker Swarm.

## ARM

- Create a C1 machine at scaleway.com
- Run the following steps

```bash
git clone https://github.com/docker/docker
cd docker
make deb
ls bundles/17.04.0-dev/build-deb/
```

- Copy the Raspbian package back to your Raspberry Pis
- Install the package

```bash
wget https://github.com/sealsystems/arm-docker-engine-deb/releases/download/git20170308.175228.0.3fe2730/docker-engine_17.04.0.dev.git20170308.175228.0.3fe2730-0.raspbian-jessie_armhf.deb
sudo dpkg -i docker-engine_17.04.0.dev.git20170308.175228.0.3fe2730-0.raspbian-jessie_armhf.deb
```

## ARM64

- Create a Type 2A machine at packet.net
- Run the following steps

```bash
apt-get update
apt-get install -y git make docker.io
systemctl start docker
git clone https://github.com/docker/docker
cd docker
git fetch origin pull/31193/head:pr31193
git checkout pr31193
git rebase master
make deb
ls bundles/17.04.0-dev/build-deb/
```

- Copy the deb packages back to your 64bit Raspberry Pis
- Install the package

```bash
wget https://github.com/sealsystems/arm-docker-engine-deb/releases/download/gitTBD/docker-engine_17.04.0.dev.TBD.deb
sudo dpkg -i docker-engine_17.04.0~dev~TBD.deb
```
