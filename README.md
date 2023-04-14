# Oracle Linux 8 Image

[![CI][Actions]][ActionsBuild] [![Docker pulls][DockerImg]][Docker]

Oracle Linux 8 Docker container for Ansible playbook and role testing.

## Tags

  - `latest`: Latest stable version of Oracle Linux 8

The latest tag is a lightweight image for basic validation of Ansible playbooks.

## How to Build

This image is built on Docker Hub automatically any time the upstream OS container is rebuilt, and any time a commit is made or merged to the `master` branch. But if you need to build the image on your own locally, do the following:

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. `cd` into this directory.
  3. Run `docker build -t oraclelinux8-base .`

## How to Use

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. Pull this image from Docker Hub: `docker pull pedigreetechnologies/docker-oraclelinux8-base:latest` (or use the image you built earlier, e.g. `oraclelinux8-base:latest`).
  3. Run a container from the image: `docker run --detach --privileged --volume=/sys/fs/cgroup:/sys/fs/cgroup:rw --cgroupns=host pedigreetechnologies/docker-oraclelinux8-base:latest`

## Notes

I use Docker to test my Ansible roles and playbooks on multiple OSes using CI tools like Jenkins and Travis. This container allows me to test roles and playbooks using Ansible running locally inside the container.

> **Important Note**: I use this image for testing in an isolated environment—not for production—and the settings and configuration used may not be suitable for a secure and performant production environment. Use on production servers/in the wild at your own risk!

## Author

Originally created in 2021 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
Adapted for internal use at Pedigree Techologies in 2023.

[Actions]: https://github.com/PedigreeTechnologies/docker-oraclelinux8-base/workflows/Build/badge.svg?branch=master&event=push
[ActionsBuild]: https://github.com/PedigreeTechnologies/docker-oraclelinux8-base/actions?query=workflow%3ABuild
[DockerImg]: https://img.shields.io/docker/pulls/pedigreetechnologies/docker-oraclelinux8-base
[Docker]: https://hub.docker.com/r/pedigreetechnologies/docker-oraclelinux8-base
