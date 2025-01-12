#  Ansible Configuration for Deployment
Ansible is used to automate the deployment and management of the Dockerized e-commerce application. Below is an overview of the Ansible playbook:

  ---
- name: Deploy E-commerce Application
  hosts: webservers
  become: yes

  tasks:
    # Install Docker
    - name: Install Docker
      apt:
        name: docker.io
        state: present

    # Install Docker Compose
    - name: Install Docker Compose
      get_url:
        url: https://github.com/docker/compose/releases/download/1.29.2/docker-compose-`uname -s`-`uname -m`
        dest: /usr/local/bin/docker-compose
        mode: '0755'

    # Clone Application Repository
    - name: Clone the application repository
      git:
        repo: https://github.com/nahorfelix/yolo/ecommerce-app.git
        dest: /opt/ecommerce-app

    # Copy Docker Compose file
    - name: Copy Docker Compose file
      copy:
        src: /local/path/docker-compose.yml
        dest: /opt/ecommerce-app/docker-compose.yml

    # Start Application
    - name: Start Docker containers
      command: docker-compose up -d
      args:
        chdir: /opt/ecommerce-app

#  Key Features

    Install Docker:
        Ensures Docker is installed on the target servers.
    Install Docker Compose:
        Downloads and sets up Docker Compose for managing multi-container applications.
    Clone Repository:
        Fetches the latest version of the application code from the specified Git repository.
    Deploy Application:
        Copies the docker-compose.yml file to the server and starts the containers.

 #  Usage
    Save the playbook as deploy.yml.
    Define target servers in the inventory file (e.g., inventory.ini).
    Run the playbook: 
    ansible-playbook -i inventory.ini deploy.yml
# Playbook Explanation

    Name: The playbook has a clear and descriptive name.
    Hosts: Targeting all ensures flexibility, but for a production setup, you might want to target specific groups (e.g., frontend, backend, database) from your inventory.
    Become: Elevating privileges (become: true) is necessary for tasks like installing Docker or managing services.
    Roles: Modularized roles (frontend-deployment, setup-mongodb, backend-deployment) make the playbook easy to maintain and extend.