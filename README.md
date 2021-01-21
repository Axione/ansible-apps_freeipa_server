# Ansible Role: ansible-apps_freeipa_server


## Description

[![Build Status](https://travis-ci.com/lotusnoir/ansible-apps_freeipa_server.svg?branch=master?style=flat)](https://travis-ci.com/lotusnoir/ansible-apps_freeipa_server)
[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen?style=flat)](https://opensource.org/licenses/Apache-2.0)
[![Ansible Role](https://img.shields.io/badge/galaxy-apps_freeipa_server-purple?style=flat)](https://galaxy.ansible.com/lotusnoir/apps_freeipa_server)
![GitHub repo size](https://img.shields.io/github/repo-size/lotusnoir/ansible-apps_freeipa_server?color=orange&style=flat)
![Ansible Quality Score](https://img.shields.io/ansible/quality/52300)
[![downloads](https://img.shields.io/ansible/role/d/52300)](https://galaxy.ansible.com/lotusnoir/apps_freeipa_server)
[![Version](https://img.shields.io/github/release/lotusnoir/ansible-apps_freeipa_server.svg)](https://github.com/lotusnoir/ansible-apps_freeipa_server/releases/)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_freeipa_server&metric=alert_status)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_freeipa_server)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_freeipa_server&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_freeipa_server)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_freeipa_server&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_freeipa_server)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=lotusnoir_ansible-apps_freeipa_server&metric=security_rating)](https://sonarcloud.io/dashboard?id=lotusnoir_ansible-apps_freeipa_server)

Deploy freeipa_server app using ansible on centos.

## Requirements

if you are in a debian system, ensure to have python-firewalld package installed on your local system in order to execute firewald module.

## Role variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `freeipa_server_type` | master | master or replica |
| `freeipa_server_admin_password` | "strongpassword" | set a strong password for the admin access |
| `freeipa_server_ds_password` | "strongpassword" | |
| `freeipa_server_domain` | example.com | set the company domain|
| `freeipa_server_realm` | EXAMPLE.COM | same as {{ freeipa_server_domain }} but upper |
| `freeipa_server_install_options` | | |
| `freeipa_client_install_options` | | |
| `freeipa_replica_install_options` | | |

## Examples

	---
	- hosts: apps_freeipa_server
	  become: yes
	  become_method: sudo
	  gather_facts: yes
	  roles:
	    - role: ansible-apps_freeipa_server
	  vars:
        freeipa_server_admin_password: "strongpassword"
        freeipa_server_ds_password: "strongpassword"
        freeipa_server_domain: "example.com"
	  environment: 
	    http_proxy: "{{ http_proxy }}"
	    https_proxy: "{{ https_proxy }}"
	    no_proxy: "{{ no_proxy }}


## License

This project is licensed under Apache License. See [LICENSE](/LICENSE) for more details.
