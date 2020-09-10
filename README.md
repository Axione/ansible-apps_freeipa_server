# Ansible Role: apps_freeipa_server


## Description

[![Build Status](https://travis-ci.com/lotusnoir/apps_freeipa_server.svg?branch=master)](https://travis-ci.com/lotusnoir/apps_freeipa_server)[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)[![Ansible Role](https://img.shields.io/badge/ansible%20role-apps__freeipa_server-blue)](https://galaxy.ansible.com/lotusnoir/apps_freeipa_server/)[![GitHub tag](https://img.shields.io/badge/version-latest-blue)](https://github.com/lotusnoir/apps_freeipa_server/tags)

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
	    - role: apps_freeipa_server
	  vars:
        freeipa_server_admin_password: "strongpassword"
        freeipa_server_ds_password: "strongpassword"
        freeipa_server_domain: "example.com"
	  environment: 
	    http_proxy: "{{ http_proxy }}"
	    https_proxy: "{{ https_proxy }}"
	    no_proxy: "{{ no_proxy }}


## License

This project is licensed under MIT License. See [LICENSE](/LICENSE) for more details.
