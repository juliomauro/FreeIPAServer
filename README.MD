# Install an configure Free IPA Server

Centralize the authentication of your linux servers with Free IPA and have full access control on your server farm, use this playbook to install and configure a Free IPA server on your linux server. 

# What we will do
  - Configure server hostname
  - Install Free IPA packages via yum (Ubuntu under construction)
  - Configure a Free IPA domain
  - Create and configure a Free IPA DNS server
  - Create and configure a Free IPA NTP server
### Prerequisites
* CentOS Server (Setup for Ubuntu soon)
* Ansible and ansible-playbook (!)

### Files that must be changed before playbook execution.

#### - [hosts](https://github.com/juliomauro/FreeIPAServer/blob/master/hosts)

```
[FreeIPAServer]
192.168.122.16 # Server IP 
[FreeIPAServer:vars]
ansible_ssh_user=root # User with permissions to install and execute free ipa install - SSH
ansible_ssh_pass=abc@123 # Password - SSH
# Ansible connection type
ansible_connection=ssh
```
#### - [default.yml](https://github.com/juliomauro/FreeIPAServer/blob/master/roles/ipaserver-install/vars/default.yml)
```
ipaserver_domain: "blablebli.cloud" # change domain
ipaadmin_password: "12qwaszx" # change password
```
### Run
 ```
 ansible-playbook FreeIPAServer.yml -e hostname=<SET-SERVER-HOSTNAME>
 ```

### Comming soon

- Free IPA server replica
- Free IPA clients install

# Maintainer - Julio Cesar Mauro
- e-mail: <juliomauro@gmail.com>
- linkedin: <https://linkedin.com/in/juliomauro>
