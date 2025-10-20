# Jenkins + Ansible + NGINX Deployment

Automated deployment of NGINX to Ubuntu server using Jenkins pipeline and Ansible.

## Architecture
- **Jenkins**: CI/CD orchestration
- **Ansible**: Configuration management
- **Target**: Ubuntu VM (Multipass)

## Files
- `Jenkinsfile`: Pipeline definition
- `ansible/playbook.yml`: NGINX installation playbook
- `ansible/inventory.ini`: Target server inventory
- `ansible/ansible.cfg`: Ansible configuration

## Deployment Flow
1. Jenkins pulls code from GitHub
2. Ansible tests SSH connection
3. Ansible installs NGINX on target server
4. Verification that NGINX is running
