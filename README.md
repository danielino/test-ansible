# test-ansible

## configure variables for digitalocean

to create droplet in digitalocean we need to copy `vars/digitalocean.yml.sample` in `vars/digitalocean.yml` and specify **api_token** and **ssh_keys** values.


## Run

```bash
DO_API_TOKEN=xyz ansible-playbook -i inventory.do playbooks/site.yml
```