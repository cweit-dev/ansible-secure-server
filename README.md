# ansible-secure-server

A single Ansible playbook that applies the minimal secure baseline I use on every Ubuntu 24.04 server.

Applied changes
- Administrative user with key-only authentication
- SSH password authentication and root login disabled
- fail2ban installed
- UFW allowing SSH only from a defined management subnet
- Unattended security updates enabled
- Timezone set to UTC

Requirements
- Ansible ≥ 2.14 (installed via pip or apt)
- Target host reachable via SSH as a user with passwordless sudo (default cloud images)

Usage
1. Edit vars/main.yml with your username, public key, and management subnet
2. Run: ansible-playbook -i inventory.ini secure-server.yml

The playbook is intentionally small and readable. Additional hardening belongs in separate roles.

Carl Weitzel
CompTIA Cloud+ | Seeking Helpdesk / Junior Sysadmin position
