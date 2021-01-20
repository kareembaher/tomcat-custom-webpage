# tomcat-custom-webpage
 
Hello,

This repo is for installtion on Tomcat9 and creating a custom page using Ansible

## Prerequisits
- You will need to install Ansible on you system, please refer to this URL https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

## How to use:
- First, you will need to edit the hosts file which is located in `/etc/ansible/hosts` and add the IPs or hostnames of the servers you want to add users on like that for example:
```
[set-of-servers]
ip-1
ip-2
```
- Secondly, you will need to change in the `configure-remote.yml` file, the `hosts` parameter to match the group you created in the hosts file. Also you will need to change the `remote_user` paramter with the remote user you will use in the remote servers.
- Or, if you want to run it locally, please use `configure-localhost.yml` file
- Finally, if you have a webpage you want to display, please replacce the file `index.html` in `roles/tomcat/files`, please note that the file must be name `index.html`
- I also changed the default Tomcat port to 9095, if you want to change it, please change the parameter `Connector port="9095"` and change the port with the one you want.
- Now you are ready to use the script using this command `ansible-playbook configure.yml`
- After the script finishes working, you can access your webpage by `server-ip:9095` if you ran `configure-remote.yml` or `localhost:9095` if you ran `configure-localhost.yml`