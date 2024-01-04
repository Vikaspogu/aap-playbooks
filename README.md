# Ansible Automation Platform Playbooks

This repository contains playbooks to automate the following tasks on proxmox virtualization:

- RHEL 9 VM template using the cloud-init
- Configure VM to install the Ansible automation platform
- Install AAP using redhat-cop [aap_utilities](https://github.com/redhat-cop/aap_utilities)
- Configure Job and Workflow templates using [awx](https://docs.ansible.com/ansible/latest/collections/awx/awx/index.html) modules
  - Workflow template to create three node openshift cluster

## Resources

- Generate offline [token](https://access.redhat.com/articles/3626371)
