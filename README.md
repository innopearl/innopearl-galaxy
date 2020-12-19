# innopearl-galaxy

## Purpose: 
Install all required docker roles on the machine define in hosts file
ansible-playbook -i hosts docker.yml --ask-sudo-pass -vvv

## Outcome
This is equivelent to ssh to each docker host and executing following playbook
  play #1 (dockers): dockers    TAGS: []
    tasks:
      geerlingguy.pip : Ensure Pip is installed.        TAGS: []
      geerlingguy.pip : Ensure pip_install_packages are installed.      TAGS: []
      include_tasks     TAGS: []
      include_tasks     TAGS: []
      geerlingguy.docker : Install Docker.      TAGS: []
      geerlingguy.docker : Ensure containerd service dir exists.        TAGS: []
      geerlingguy.docker : Add shim to ensure Docker can start in all environments.     TAGS: []
      geerlingguy.docker : Reload systemd daemon if template is changed.        TAGS: []
      geerlingguy.docker : Ensure Docker is started and enabled at boot.        TAGS: []
      include_tasks     TAGS: []
      include_tasks     TAGS: []
      grafana   TAGS: []
      influxdb  TAGS: []
      telegraf  TAGS: []

As consequence following ansible roles will be available on the dockers machines:
- geerlingguy.pip
- geerlingguy.docker
- grafana
- influxdb
- telegraf 

