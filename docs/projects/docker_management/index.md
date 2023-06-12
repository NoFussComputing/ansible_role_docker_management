---
title: Docker Management from configuration as code
description: How to use No Fuss Computings Ansible role to manage docker from configuration as code.
date: 2023-06-10
template: project.html
about: https://gitlab.com/nofusscomputing/projects/ansible/execution_environment
---


This Ansible role is designed to manage Docker and related items, providing installation, configuration, and management of Docker networks, volumes, images, and containers. It aims to simplify the process of managing Docker environments and allows for flexible customization based on your specific requirements.


## Design

The `docker_management` role follows a modular approach, organizing its tasks into separate files based on their respective functionalities. This design makes it easy to understand and maintain the role, as well as allowing for flexibility in customizing different aspects of Docker management.

The role includes the following task files:

- `install_docker.yml`: Installs Docker using the package manager on supported operating systems.

- `configure_docker_daemon.yml`: Configures the Docker daemon with the specified settings.

- `manage_docker_networks.yml`: Manages Docker networks, creating, updating, or removing them as needed.

- `manage_docker_volumes.yml`: Manages Docker volumes, creating, updating, or removing them as needed.

- `manage_docker_images.yml`: Manages Docker images, pulling, building, pushing, or removing them as specified.

- `manage_docker_containers.yml`: Manages Docker containers, creating, starting, stopping, or removing them as required.

The role also includes a `handlers` directory that contains the `main.yml` file defining the handler tasks. These handlers are triggered when specific events occur, such as restarting Docker after configuration changes.

To provide flexibility and customization, the role utilizes variables defined in the `defaults/main.yml` file. These variables allow you to configure various aspects of Docker management, including the installation options, Docker daemon configuration, Docker networks, volumes, images, and containers.


## Requirements

To use the `docker_management` role, the following requirements must be met:

- Ansible version 2.10 or later.

- The [community.docker collection](https://galaxy.ansible.com/community/docker) is required. You can install it using the following command:

```bash
ansible-galaxy collection install community.docker
```


## Role Variables

The `docker_management` role provides the following variables that can be customized in your playbook:


### `docker_installation_options`

A list of dictionaries specifying the Docker installation options. Each dictionary represents a package to be installed and its state.


#### Parameters:

- `name`: (required) The name of the package to install.

- `state`: (required) The desired state of the package. Accepted values are `present`, `absent`, `latest`, or a specific version.

For more information, refer to the [docker_package module documentation](https://docs.ansible.com/ansible/latest/collections/community/docker/docker_package_module.html).

Example:

```yaml
docker_installation_options:
  - name: docker
    state: present
```


### `docker_daemon_config`

A dictionary containing the configuration options for the Docker daemon.


#### Parameters:

- `log-driver`: (optional) The log driver for Docker containers.

- `log-opts`: (optional) Additional options for the log driver.

For more information, refer to the [docker_daemon module documentation](https://docs.ansible.com/ansible/latest/collections/community/docker/docker_daemon_module.html).

Example:

```yaml
docker_daemon_config:
  log-driver: json-file
  log-opts:
    max-size: "10m"
    max-file: "3"
```


### `docker_networks`

A list of dictionaries representing the Docker networks to be managed.


#### Parameters:

- `name`: (required) The name of the network.

- `state`: (required) The desired state of the network. Accepted values are `present` or `absent`.

- `driver`: (optional) The driver to use for the network. Default is Docker's default bridge driver.

- `enable_ipv6`: (optional) Enable IPv6 on the network. Default is `no`.

- `options`: (optional) Additional options for the network.

- `labels`: (optional) Labels to assign to the network.

For more information, refer to the [docker_network module documentation](https://docs.ansible.com/ansible/latest/collections/community/docker/docker_network_module.html).

Example:

```yaml
docker_networks:
  - name: my_network
    state: present
    driver: bridge
    enable_ipv6: no
    options:
      com.docker.network.bridge.name: my_bridge
    labels:
      env: production
```


### `docker_volumes`

A list of dictionaries representing the Docker volumes to be managed.


#### Parameters:

- `name`: (required) The name of the volume.

- `state`: (required) The desired state of the volume. Accepted values are `present` or `absent`.

- `driver`: (optional) The driver to use for the volume. Default is Docker's default volume driver.

- `driver_options`: (optional) Additional options for the volume driver.

- `labels`: (optional) Labels to assign to the volume.

For more information, refer to the [docker_volume module documentation](https://docs.ansible.com/ansible/latest/collections/community/docker/docker_volume_module.html).

Example:

```yaml
docker_volumes:
  - name: my_volume
    state: present
    driver: local
    driver_options:
      type: nfs
      o: addr=192.168.0.100,rw
    labels:
      env: production
```


### `docker_images`

A list of dictionaries representing the Docker images to be managed.


#### Parameters:

- `name`: (required) The name of the image.

- `tag`: (optional) The tag of the image. Default is `latest`.

- `source`: (optional) The source of the image. Can be either a local image or a remote image from a registry.

- `pull`: (optional) Whether to pull the image if it is not present. Default is `yes`.

- `build`: (optional) Build options for the image.

- `push`: (optional) Whether to push the image to a registry. Default is `no`.

- `force_source`: (optional) Whether to force pulling or building the image. Default is `no`.

- `force`: (optional) Whether to force removing and re-creating the container if it already exists. Default is `no`.

- `remove`: (optional) Whether to remove the image after running a container using it. Default is `no`.

- `source_directory`: (optional) The directory containing the Dockerfile and build context for building the image.

For more information, refer to the [docker_image module documentation](https://docs.ansible.com/ansible/latest/collections/community/docker/docker_image_module.html).

Example:

```yaml
docker_images:
  - name: nginx
    tag: latest
    pull: yes
    build:
      path: /path/to/build/context
      pull: yes
      nocache: no
      buildargs:
        HTTP_PROXY: http://proxy.example.com
      labels:
        env: production
    push: no
```


### `docker_containers`

A list of dictionaries representing the Docker containers to be managed.


#### Parameters:

- `name`: (required) The name of the container.

- `image`: (required) The name of the image to use for the container.

- `state`: (required) The desired state of the container. Accepted values are `present`, `absent`, `started`, `stopped`, or `restarted`.

- `command`: (optional) The command to run inside the container.

- `entrypoint`: (optional) The entrypoint for the container.

- `ports`: (optional) The ports to expose on the container.

- `volumes`: (optional) The volumes to mount on the container.

- `environment`: (optional) Environment variables for the container.

- `restart_policy`: (optional) The restart policy for the container.

- `restart_retries`: (optional) The number of times to retry restarting the container.

- `labels`: (optional) Labels to assign to the container.

- `log_driver`: (optional) The log driver for the container.

- `log_options`: (optional) Additional options for the log driver.

- `healthcheck`: (optional) Healthcheck options for the container.

- `depends_on`: (optional) The containers the current container depends on.

- `cap_drop`: (optional) The Linux capabilities to drop for the container.

- `cap_add`: (optional) The Linux capabilities to add for the container.

- `privileged`: (optional) Whether to run the container in privileged mode.

- `network_mode`: (optional) The network mode for the container.

- `networks`: (optional) The networks the container should connect to.

- `dns_servers`: (optional) The DNS servers to use for the container.

- `dns_search_domains`: (optional) The DNS search domains to use for the container.

For more information, refer to the [docker_container module documentation](https://docs.ansible.com/ansible/latest/collections/community/docker/docker_container_module.html).

Example:

```yaml
docker_containers:
  - name: my_container
    image: nginx
    state: started
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - /host/path:/container/path
    environment:
      MY_VAR: value
    restart_policy: always
    labels:
      env: production
    log_driver: json-file
    log_options:
      max-size: "10m"
      max-file: "3"
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost/"]
      interval: 30s
      timeout: 10s
      retries: 3
    depends_on:
      - another_container
    networks:
      - my_network
    dns_servers:
      - 8.8.8.8
    dns_search_domains:
      - example.com
```


## Example Playbook

Here's an example playbook that demonstrates how to use the `docker_management` role:

```yaml
- name: Manage Docker environment
  hosts: all
  become: true

  roles:
    - docker_management
```
