# MongoDB and Backup with VPN Setup

This project sets up a MongoDB instance on one VM, backups on another, and a VPN connection between the two VMs using Vagrant and Ansible.

## Vagrantfile
The Vagrantfile sets up two Ubuntu VMs:
- `mongo`: Runs MongoDB.
- `backup`: Configured to take regular backups from the `mongo` VM.

## Ansible Playbooks
- `mongo_setup.yml`: Installs and configures MongoDB on the `mongo` VM.
- `backup_setup.yml`: Sets up a cron job on the `backup` VM to regularly backup MongoDB data.
- `vpn_setup.yml`: Configures OpenVPN on the `mongo` VM to allow secure connections from the `backup` VM.

## Steps to Run
1. Clone the repository.
2. Run `vagrant up` to start the VMs and provision them using Ansible.
3. Connect to the VPN from the `backup` VM to the `mongo` VM.

## Backup Location
Backups are stored in `/vagrant/backups` directory on the `backup` VM.

## VPN
The VPN setup ensures that all communications between the two VMs are secure.

