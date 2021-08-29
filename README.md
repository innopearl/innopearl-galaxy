# innopearl-galaxy

## Purpose: 
Install all required docker roles on the machine define in hosts file
ansible-playbook -i hosts docker.yml --ask-sudo-pass -vvv

## Steps:
Run playbook in following orders
| Order | Playbook | Comments |
|-------|----------|----------|
| 01 | install_packages.centos.yml | Setup package repos and install some essential packages |
| 02 | settings.yml | Setup the user working environment: .vimrc, .bashrc, etc... |
| 03 | docker-compose | run it for each sub directory in docker: docker/grafana, docker/bind, etc... |

## Desired
- grafana
- influxdb
- telegraf 

