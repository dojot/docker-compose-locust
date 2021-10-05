# Dojot Load Test - Docker compose
This repository contains the necessary configuration files
for quick deployment of the Dojot Load Test tool using docker-compose.

# **How to use**

## **Prerequisites**

If you don't have any certificates, you should first generate them. See the
Generate Certificates script [documentation](https://github.com/dojot/dojot/tree/master/connector/mqtt/locust/src/scripts/README.md) for more info.

For instructions on how to configure and how to it works, please check the [documentation](https://github.com/dojot/dojot/tree/master/connector/mqtt/locust/README.md) or follow the [tutorial](https://dojotdocs.readthedocs.io/en/latest/load-testing-dojot-platform.html).

## **Docker-Compose**

**Remember to change the environment variables to your needs before continuing.**

In Locust root directory, bring up the master node:

```shell
docker-compose -f docker-compose-master.yml up
```

After the complete initialization of the master node, run the slave:

```shell
docker-compose -f docker-compose-slave.yml up
```

You can also run more than one slave at once:

```shell
docker-compose -f docker-compose-slave.yml up --scale locust-slave=10
```

We recommend running no more slaves than the number of cores in your hardware.

To run the generate_certs container, simply run the following command:
```shell
docker-compose -f docker-compose-generate_certs.yml up -d
```
