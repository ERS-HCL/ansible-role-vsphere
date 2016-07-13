ansible-role-vsphere
====================

An Ansible role that creates Virtual machines in the vmware virtualization environment. 
IP address of the virtual machines are updated in the inventory file for further use in other roles/playbook. 

Requirements
------------

pysphere package installed on the ansible machine.
Vmware vCenter environment is configured and available. 
Template version of the virtual machine is available in the vCenter for deployment

Role Variables
--------------

Available Variables are listed below 

	vsphere_vcenter_hostname: "vcenter1"
  	vsphere_vcenter_username: "root"
	vsphere_vcenter_password: "passwd"
  VCenter server name/IP address and the credentials to connect to the vCenter Server. 

	vsphere_datacenter_name: "datacenter1"
	vsphere_esxi_host: "esx1"
  Datacenter under which the virtual machines will be created and the ESXi server to associate the virtual machines. 

	vsphere_datastore_name: "datastore1"
  Datastore name where the hard disk for the virtual machine will be stored

	vsphere_template_name: "centos_template"
  Preinstalled OS image template that will get installed

Host variable in the inventory file are listed below with default values

	[hosts]
  Group name to collect the list of virutual machine names in the inventory file

	<vm name> cpu=2 memory=4096 disk=20
  Name of the virutal machine required, number of virtual cpus required, memory size in MB, disk size in GB 

Dependencies
------------

 None

Example Playbook
----------------

    - hosts: hosts
      connection: local
      vars:
        vsphere_vcenter_hostname: "vcenter1"
        vsphere_vcenter_username: "root"
        vsphere_vcenter_password: "passwd"
        vsphere_datacenter_name: "datacenter1"
        vsphere_esxi_host: "esx1"
        vsphere_datastore_name: "datastore1"
        vsphere_template_name: "centos_template"

      roles:
         - SathiyarajPeriyannan.vsphere 

License
-------

BSD

Author Information
------------------

This role was created in 2016 by Sathiyaraj Periyannan 
