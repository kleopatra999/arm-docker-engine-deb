# armhf-docker-engine-deb
Raspbian package of docker-engine for ARM

This is a short documentation how to build the docker-engine Raspbian package for ARM from master branch.

- Create a C1 machine at scaleway.com
- Run the following steps

```bash
git clone https://github.com/docker/docker
cd docker
make deb
ls bundles
```

- Copy the Raspbian package back to your Raspberry Pis
- Install the package

```bash
sudo dpkg -i docker-engine_17.04.0~dev~git20170308.175228.0.3fe2730-0~raspbian-jessie_armhf.deb
```
