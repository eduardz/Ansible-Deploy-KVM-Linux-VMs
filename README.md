#####
Deploy VirtualMachines in Linux KVM server with Ansible playbook<br />

Variables are stored in "roles/ansible-deploy-vms/vars/main.yml"<br />

Get OSs names with:
```
virt-builder --list
opensuse-tumbleweed      x86_64     openSUSE Tumbleweed
alma-8.5                 x86_64     AlmaLinux 8.5
centos-7.8               x86_64     CentOS 7.8
centos-8.2               x86_64     CentOS 8.2
centosstream-8           x86_64     CentOS Stream 8
centosstream-9           x86_64     CentOS Stream 9
debian-11                x86_64     Debian 11 (bullseye)
fedora-37                x86_64     Fedora® 37 Server
ubuntu-20.04             x86_64     Ubuntu 20.04 (focal)
```
guests:
  kubernetes_master01:
    mem: 1024
    cpus: 1
    os_template: debian-11
    os_type: linux
    file_type: qcow2
    disk_size: 10G
  kubernetes_slave01:
    mem: 1024
    cpus: 1
    os_template: fedora-37
    os_type: linux
    file_type: qcow2
    disk_size: 20G

  kubernetes_slave02:
    mem: 1024
    cpus: 1
    os_template: fedora-37
    os_type: linux
    file_type: qcow2
    disk_size: 20G
  kubernetes_slave03:
    mem: 1024
    cpus: 1
    os_template: fedora-37
    os_type: linux
    file_type: qcow2
    disk_size: 20G
```

#### deply VMs with password<br />
```ansible-playbook -i inventory kvm.yml -K``` 


#### deply VMs with public key<br />
```ansible-playbook -i inventory kvm.yml``` 


