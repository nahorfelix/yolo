# Overview
This project involved the containerization and deployment of a full-stack yolo application using Docker.
Ensure the following tools are installed:
  1.Vagrant
  2. VirtualBox
  3. Ansible
  4.Docker
  5.Git
Clone the Repository
example 
git clone https://github.com/nahorfelix/yolo.git
 cd yolo

# Start the Virtual Machine
Use vagrant up --provison command
# Run Ansible Playbook
ansible-playbook -i ansible/inventory/hosts.ini ansible/playbook.yml

# Run Docker Compose
docker-compose up --build
# Configuration Files
  inventory File (ansible/inventory/hosts.ini)
  # Defines the target hosts for Ansible.
  Playbook File 
  # Defines tasks for setting up and deploying the application.

  # commits 



