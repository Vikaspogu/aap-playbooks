# Ansible Automation Platform Playbooks

This repository contains playbooks to automate the following tasks on proxmox virtualization:

- RHEL 9 VM template using the cloud-init
- Configure VM to install the Ansible automation platform
- Install AAP using redhat-cop [aap_utilities](https://github.com/redhat-cop/aap_utilities)
- Configure Job and Workflow templates using [awx](https://docs.ansible.com/ansible/latest/collections/awx/awx/index.html) modules
  - Workflow template to create three node openshift cluster

## Prepare, Download & Setup AAP

```yaml
ansible-playbook -i inventory/hosts.yaml playbooks/aap-controller/create.yaml -e "aap_setup_down_offline_token=..."
```

## Configure AAP

```yaml
ansible-playbook playbooks/aap-controller/config.yaml
```

## Resources

- Generate offline [token](https://access.redhat.com/articles/3626371)
- [API](https://access.redhat.com/management/api) documentation
