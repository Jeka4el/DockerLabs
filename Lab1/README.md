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


## Commands

1. docker network create web_network
2. cd Lab1
3. docker build -t ansible_server -f Dockerfile.ansible .
4. docker build -t apache_server -f Dockerfile.apache .
5. docker run -d --network web_network --name web1 apache_server
6. docker run -d --network web_network --name web2 apache_server
7. docker run -d --network web_network --name web3 apache_server
8. docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' web1
9. copy ip and upserve web page using browser or curl.
10. docker run -it --network web_network --name ansible ansible_server bash
11. ansible-playbook update_web.yml
12. copy ip again and upserve web page using browser or curl.
