# Vagrant Ansible LEMP

A Linux, NGINX, MySQL, and PHP (LEMP) Vagrant box for web development based on 'ubuntu/xenial64' -- the official Ubuntu 16.04 LTS (Xenial Xerus) Daily Build --
 and provisioned (somewhat long-windedly) with Ansible.

## Background

First and foremost this project is an exercise in provisioning a Vagrant box
using Ansible as envisioned by a novice. Gratuitous comments and lengthy
configuration blocks serve to provide a greater amount of context.

## Getting Started

### Prerequisites

* [Virtualbox](https://www.virtualbox.org/) >= 4.0.0
* [Vagrant](https://www.vagrantup.com/) >= 1.7.0
* [Ansible](https://www.ansible.com/) >= 2.0

Minimum versions are educated guesses.

### Usage

Download roles from Ansible Galaxy:
```
ansible-galaxy install -r requirements.yml
```

Download, configure, and provision Vagrant box:
```
vagrant up
```

## Additional Information

### Ports

| Service | Host Port | VM Port |
|---------|----------:|--------:|
| HTTP    | 8080      | 80      |
| MySQL   | 33060     | 3306    |

### Credentials

| Service | Username | Password |
|---------|----------|----------|
| MySQL   | vagrant  | secret   |

### Features

* NGINX: Create and set document root per `document_root` variable
* MySQL: Permissive user host and 'all interface' bind-address for remote MySQL server connection from Vagrant host

## TODO

* Try templating
* Implement testing strategies
