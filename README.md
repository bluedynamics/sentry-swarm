# Sentry in a Docker Swarm

An inofficial bootstrap for running [Sentry](https://sentry.io/) with [Docker](https://www.docker.com/) in a Docker Swarm, like self hosted.

## Requirements

* Docker 20.10.16+ (tested)
* 2 CPU Cores (better 4)
* ~8 GB RAM
* ~20 GB Free Disk Space

## Preparation

### GeoIP

1. In order to use the Maxmind GeoIP feature they must create a file named `config/GeoIP.conf` following the procedures as described here (free):
https://dev.maxmind.com/geoip/updating-databases?lang=en

2. (TODO) Copy initial DB


### Relay Configuration

Copy `config/relay.example.yml` as `config/relay.yml` and change if needed (usually not necessary).


### Symbolicator Configuration

Copy `config/symbolicator.example.yml` as `config/symbolicator.yml` and change if needed (usually not necessary).


### Clickhouse Configuration

Copy `config/clickhosue.example.xml` as `config/clickhosue.xml` and change if needed (usually not necessary).

### Set environment

Edit the `.env` file and adopt it to your needs.


## Installation

Given a docker swarm is configured, run:

```
source .env
docker stack deploy sentry -c sentry-swarm.yml
```