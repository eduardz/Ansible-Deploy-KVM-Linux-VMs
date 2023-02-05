#####
Deploy VirtualMachines in Linux KVM server with Ansible playbook<br />

Variables are stored in "roles/ansible-deploy-vms/vars/main.yml"<br />

Get OSs names with "virt-builder --list"<br />

example for OS template:<br />
os_template: fedora-34<br />
os_template: centos-8.2<br />
os_template: centos-7.8<br />

```
guests:
  kubernetes_master01:
    mem: 1024
    cpus: 1
    os_template: centos-8.2
    os_type: linux
    file_type: qcow2
    disk_size: 10G
  kubernetes_slave01:
    mem: 1024
    cpus: 1
    os_template: centos-7.8
    os_type: linux
    file_type: qcow2
    disk_size: 20G

  kubernetes_slave02:
    mem: 1024
    cpus: 1
    os_template: centos-7.8
    os_type: linux
    file_type: qcow2
    disk_size: 20G
  kubernetes_slave03:
    mem: 1024
    cpus: 1
    os_template: centos-7.8
    os_type: linux
    file_type: qcow2
    disk_size: 20G
```

#### deply VMs with password<br />
```ansible-playbook -i inventory kvm.yml -K``` <br />

<br />
#### deply VMs with public key<br />
```ansible-playbook -i inventory kvm.yml``` 


