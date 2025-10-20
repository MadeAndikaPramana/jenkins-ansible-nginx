# Jenkins + Ansible + NGINX Deployment

Automated deployment NGINX to Ubuntu server menggunakan Jenkins pipeline dan Ansible.

## Architecture
- **Jenkins**: CI/CD orchestration
- **Ansible**: Config management
- **Target**: Ubuntu VM (Multipass)

## Files
- `Jenkinsfile`: Pipeline definition
- `ansible/playbook.yml`: NGINX installation playbook
- `ansible/inventory.ini`: Target server inventory
- `ansible/ansible.cfg`: Ansible configuration

## Deployment Flow
1. Jenkins pull code dari GitHub
2. Ansible tests SSH connection
3. Ansible installs NGINX di target server
4. Verification NGINX is running
