# CentOS7/RHEL7 Preinstaller
This role configures OS.

# Requirements
This roles was tested only on `CentOS7` or `RHEL7`.

# Role Variables
* variable file 
```
$ cat roles/ansible.rhel-preinstall/defaults/main.yaml
```

* configure timezone
```
set_timezone: Asia/Seoul
```

* configure disable `firewalld`
```
unuse_firewalld: true
```

* configure disable `NetworkManager`
```
unuse_networkmanager: true
```

* configure disable selinux
```
unuse_selinux: true
```

* configure disable `ctl+alt+del`
```
unuse_functionkey: true
```

* configure local repository (request media)
```
install_localrepo: true
```

* configure local repository location 
```
location_repo: /root/repo
```

* Your choice environment, graphical server or gnome desktop.
* configure install graphical server environment
```
install_graphical: true
```

* configure install gnome desktop environment
```
install_gnome: false
```

* choice disable libvirtd
```
unuse_libvirtd: true
```

* configure ntp service
```
install_ntp: true
```

* choice ntp package (`ntp` or `chrony`)
```
ntp_package_name: chrony
```

* create template script file
```
create_template_file: true
```

* Auto reboot system
```
reboot_system: false
```

# Example Playbook
1. git clone.
```
$ git clone https://github.com/chhanz/rhel-preinstall.git
```

2. change variables.
```
$ vi roles/ansible.rhel-preinstall/defaults/main.yaml
```

3. change inventory file
```
$ vi inventory/hosts
```

4. run ansible playbook
```
$ ansible-playbook -i inventory/hosts rhel7_preinstaller.yaml
```
