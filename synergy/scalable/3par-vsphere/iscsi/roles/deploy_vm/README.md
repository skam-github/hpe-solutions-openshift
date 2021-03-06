Role Name: deploy_vm
=========
This role creates the management and worker VMs required for the Red Hat OpenShift Container Platform deployment.
At the end, There are 3 masters, 3 infra, 2 load balance and 6 worker VMs created as part of this role.

Important: If using Bare-Metal worker nodes, comment the "- import_tasks: worker_vms.yml" line in the ..roles/deploy_vm/tasks/main.yml

Requirements
------------
- An Ansible engine with Python 2.7.9 and above, Ansible 2.7.2 and PyVmomi installed.
- A vCenter with a datacenter, compute clusters with vSphere 6.7 hosts, datastore with sufficient storage, an RHEL 7.6 template with VMware Tools installed in it.

Role Variables
--------------
---
 vars file for deploy_vm

 Name of the Datacenter 
- datacenter_name: datacenter

 Name of the compute clusters with the ESXi hosts for Management VMs and worker VMs 
- management_cluster_name: management-cluster
- worker_cluster_name: worker-cluster

 Name of the Datastore to store the VMs 
- management_datastore_name: management-datastore
- worker_datastore_name: worker-datastore

 Name of the RHEL 7.6 VM template with VMware tools installed 
- vmtemplate: rhel

 Disk size in GB/GiB
- master_disk: 100
- infra_disk: 50
- lb_disk: 50
- worker_disk: 100

 number of CPUs
- master_cpu: 4
- infra_cpu: 4
- lb_cpu: 4
- worker_cpu: 4

 Memory size in MB/MiB
- master_memory: 16400
- infra_memory: 25400
- lb_memory: 16400
- worker_memory: 16400

 datacenter network IP address of the masters, infra, lb and worker nodes
- master01_ip: 20.0.60.121
- master02_ip: 20.0.60.122
- master03_ip: 20.0.60.123
- infra01_ip: 20.0.60.124
- infra02_ip: 20.0.60.125
- infra03_ip: 20.0.60.126
- lb01_ip: 20.0.60.127
- lb02_ip: 20.0.60.128
- worker01_ip: 20.0.60.129
- worker02_ip: 20.0.60.130
- worker03_ip: 20.0.60.131
- worker04_ip: 20.0.60.132
- worker05_ip: 20.0.60.133
- worker06_ip: 20.0.60.134

 iscsi_a network IP address of the masters, infra and worker nodes
- master01_ip2: 30.0.60.121
- master02_ip2: 30.0.60.122
- master03_ip2: 30.0.60.123
- infra01_ip2: 30.0.60.124
- infra02_ip2: 30.0.60.125
- infra03_ip2: 30.0.60.126
- worker01_ip2: 30.0.60.129
- worker02_ip2: 30.0.60.130
- worker03_ip2: 30.0.60.131
- worker04_ip2: 30.0.60.132
- worker05_ip2: 30.0.60.133
- worker06_ip2: 30.0.60.134

iscsi_b network IP address of the masters, infra and worker nodes
- master01_ip3: 40.0.60.121
- master02_ip3: 40.0.60.122
- master03_ip3: 40.0.60.123
- infra01_ip3: 40.0.60.124
- infra02_ip3: 40.0.60.125
- infra03_ip3: 40.0.60.126
- worker01_ip3: 40.0.60.129
- worker02_ip3: 40.0.60.130
- worker03_ip3: 40.0.60.131
- worker04_ip3: 40.0.60.132
- worker05_ip3: 40.0.60.133
- worker06_ip3: 40.0.60.134

 name of the master, infra, lb and worker nodes < short names, not the FQDN >
- master01_name: master01
- master02_name: master02
- master03_name: master03
- infra01_name: infra01
- infra02_name: infra02
- infra03_name: infra03
- lb01_name: lb01
- lb02_name: lb02
- worker01_name: worker01
- worker02_name: worker02
- worker03_name: worker03
- worker04_name: worker04
- worker05_name: worker05
- worker06_name: worker06

 network configuration details for the datacenter network
- netmask: 255.0.0.0
- gateway: 20.x.x.x
- dns_server: 20.x.x.x
- domain_name: "twentynet.local"

 netmask for the iSCSI networks
- netmask_iscsi_a: 255.255.0.0
- netmask_iscsi_b: 255.255.0.0

 Network names for the datacenter/management, iSCSI A and iSCSI B networks
- datacenter_network_name: "VM Network"
- iscsi_a_network_name: "iSCSI-A"
- iscsi_b_network_name: "iSCSI-B"

Dependencies
------------
None

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
