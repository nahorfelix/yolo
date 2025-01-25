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

 #stage _two 
 Create a New Branch and Directory
   # Checkout to a New Branch:
    git checkout -b Stage_two
# Create a New Directory: Navigate to the root of the stage-1-Ansible-root directory and create a folder named after the new branch:
  mkdir stage_two
  cd stage_two
 cd stage _two and write the code 
 
run the entire code
#  my GCP was not working to provide a link , it failed billing 