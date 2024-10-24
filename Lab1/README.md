# Lab 1 - Web Servers and Ansible Automation

## Description

In this lab, I will create three web servers and one Ansible server (containers) in a single network using Dockerfiles. Then, I will remotely change the `index.html` file on all servers using Ansible.

## Pre-steps

1. Create a virtual machine.
2. Install Docker on the virtual machine.
3. Generate an SSH key.
4. Create a Docker network (use the command `docker network create web_network`).

## Steps

1. Create a working directory, copy the SSH key here, and create the following files.
2. Create `Dockerfile.ansible` and `Dockerfile.apache` to build Docker images.
3. Create `ansible.cfg`, `hosts.ini`, and an `update_web.yml` playbook.
