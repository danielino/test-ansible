# test-ansible

[![Build Status](https://travis-ci.com/danielino/test-ansible.svg?branch=master)](https://travis-ci.com/danielino/test-ansible)

this project allow to deploy a secure swarm cluster in digitalocean.

tasks:

- create droplet centos7 8gbram
- add 40gb block storage
- add `docker` tag to droplets
- setup dcker
- init swarm cluster
- generate and configure tls certificate to secure dockerd API 
- add tcp socket listen on tcp 2376 for remote management
- download certificate bundle for remote access
- deploy wordpress swarm service

## setup

- requirements:
    - python pip / pip3 installed

- clone repository

    ```
    $ git clone https://github.com/danielino/ansible-test.git
    $ cd ansible-test
    ```

- python2

    ```bash
    pip install -r requirements.txt
    ```

- python3

    ```bash
    pip3 install -r requirements3.txt
    ```

- digitalocean settings

    rename digitalocean.yml.sample in digitalocean.yml and configure:
    - api_keys: DigitalOcean api token
    - ssh_keys: a list of ssh keys id

    ```
    $ mv vars/digitalocean.yml.sample vars/digitalocean.yml
    $ vi vars/digitalocean.yml
    ``` 

- run!

    ```bash
    DO_API_TOKEN=xyz ansible-playbook -i inventory.do playbooks/site.yml
    ```

