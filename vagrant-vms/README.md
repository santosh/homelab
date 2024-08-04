## vagrant-vms

This directory hosts same Vagrantfile definitions for some of the VMs running on my main PC. These VMs use VirtualBox as the provider.

### Directions to use

Each subdirectory resembles a VM to be created. Before using them to provision, look for `ENV` in the definition file. For example, I have remove hardcoded value of `IP_ADDRESS` and replaced it with `ENV['IP_ADDRESS']`. This way, you can set the environment variable before running the `vagrant up` command.

For the networking bit, I like my VMs to have bridged network so that they can be accessed from other devices on the network. In this, IP address is allocated by the router/DHCP-server in my network. If you rather want to use private IP, modification is needed in the Vagrantfile.

### VMs

- **k3s-proteus**:
  - OS: Debian (Bookworm)
  - k8s worker

- **swarm-triton**:
  - OS: Debian (Bookworm)
  - swarm worker

- **kali**:
  - for occasional hacking

- **Metasploitable 2**
  - prey for kali (needs automation to setup with vagrant/terraform)

### Further Development

- [ ] Add definition for Proxmox VMs (rename the directory appropriately)
- [ ] Use generic driver for provisioning such as Terraform/Ansible
- [ ] Vagrant does not allow setting up storage constraints. Look into it.
