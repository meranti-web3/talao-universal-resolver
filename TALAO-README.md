# Talao Universal Resolver

/!\ This project is actually a fork of `https://github.com/Meeco/universal-resolver`. Make sure to keep both repositories in sync

The goal of this project is to setup a DID (decentralized identity) resolver for Talao.
It also needs to support the hedera resolver which is a plugin.

This project will be deployed directly onto a Talao managed AWS machine, this project is mainly to test and verify that things work as expected before being deployed.

1. Deployed onto a Talao managed AWS machine.
2. Uses [Universal Resolver](https://github.com/decentralized-identity/universal-resolver/blob/main/README.md)
3. Adds [Hedera plugin](https://github.com/Meeco/hedera-did-universal-resolver-driver).

## Install

Clone this repository

```sh
git clone git@github.com:meranti-web3/talao-universal-resolver.git
```

Then switch to the `talao-config` branch

```
cd talao-universal-resolver
git checkout talao-config
```

And build the docker container locally. The container pushed to the docker registry isn't configured for Hedera, so we need to build it locally.

```sh
docker build -f ./uni-resolver-web/docker/Dockerfile . -t universalresolver/uni-resolver-web
```

## Run

On Linux

```sh
docker compose pull
docker compose up
```

On Silicon Mac

```sh
DOCKER_DEFAULT_PLATFORM=linux/x86_64/v8 docker compose pull
```

```sh
DOCKER_DEFAULT_PLATFORM=linux/x86_64/v8 docker compose up
```
