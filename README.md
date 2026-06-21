# Uvaiz
This is Uvaiz 
[webservers]
localhost ansible_connection=local

---
- name: Install and start Nginx
  hosts: webservers
  become: yes

  tasks:
    - name: Install Nginx
      apt:
        name: nginx
        state: present
        update_cache: yes

    - name: Ensure Nginx is running
      service:
        name: nginx
        state: started
        enabled: yes
