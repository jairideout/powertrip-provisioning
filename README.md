# Powertrip Setup/Notes

## Getting Started

This ansible playbook is for orchestrating deployment of necessary tools.

### Setting up agent machine (e.g. dev laptop)
- install ansible 2.2
- `git clone https://github.com/caporaso-lab/powertrip-provisioning.git`
- `cd powertrip-provisioning`
- Define your inventory and host vars as necessary

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
ansible-playbook -i /path/to/inventory -K --extra-vars "cert_dir=/path/to/certs" site.yml
```
