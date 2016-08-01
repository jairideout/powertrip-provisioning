# Powertrip Setup/Notes

## Getting Started

This ansible playbook is for orchestrating deployment of necessary tools.

### Setting up agent machine (e.g. dev laptop)
- install ansible 2.1
- `git clone https://github.com/caporaso-lab/powertrip-provisioning.git`
- `cd powertrip-provisioning`
- Edit `host_vars/powertrip.yml` as necessary

### Bootstrapping the linux hosts
- Ensure SSH access is enabled on the linux host
- Set up a keypair to use for access
- From agent machine: `scp bin/bootstrap-linux-host.sh USER@LINUXHOST:~/`
- On linux host:
    - `chmod +x bootstrap-linux-host.sh`
    - `./bootstrap-linux-host.sh`
    - Follow the prompts

## Provisioning

```bash
ansible-playbook -i inventory -l powertrip site.yml
```

## Development

### Setting up local linux VM with Vagrant

```bash
vagrant up
```

Note: if you don't use Vagrant, you need to make sure that you set up private
networking and the appropriate port forwarding in your VM for everything to
work, and make sure to update the files in `host_vars` to reflect those settings.
