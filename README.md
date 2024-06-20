1. Automated Server Configuration with Ansible

**Description:** Create an Ansible playbook to automate the setup and configuration of RHEL servers.

**Example Playbook (setup.yml):**yaml
---
- name: Configure RHEL Servers
  hosts: rhel_servers
  become: true
  tasks:
    - name: Ensure Apache is installed
      yum:
        name: httpd
        state: present

    - name: Copy Apache configuration file
      copy:
        src: files/httpd.conf
        dest: /etc/httpd/conf/httpd.conf
        owner: root
        group: root
        mode: '0644'

    - name: Start Apache service
      service:
        name: httpd
        state: started
        enabled: true
**Project Steps:**
Install Ansible on your local machine.
Create a directory structure for your Ansible project.
Write the playbook (setup.yml) with tasks to install Apache, copy configuration files, and start the service.
Define inventory (hosts) file to specify target servers.
Run the playbook and verify Apache installation and configuration on RHEL servers.
