## Centos7 docker image for testing ansible roles
[![Build Status](https://travis-ci.org/lestex/docker-centos7-ansible.svg?branch=master)](https://travis-ci.org/lestex/docker-centos7-ansible)

### How to Build

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. clone this repo
  3. `cd` into `docker-centos7-ansible`.
  4. Run `docker build -t centos7 .`

### How to run

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. Pull this image from Docker Hub: `docker pull lestex/docker-centos7-ansible`. Use the `latest` tag.
  3. Run a container from the image: 
  ```
  docker run -d --name test --privileged -v=/sys/fs/cgroup:/sys/fs/cgroup:ro lestex/docker-centos7-ansible /lib/systemd/systemd
```
  4. Use Ansible inside the container:
  
```
docker exec -it test ansible --version
docker exec -it test ansible-lint /path/to/ansible/playbook.yml
```

### Author

Created by [Andrey Larin]()
