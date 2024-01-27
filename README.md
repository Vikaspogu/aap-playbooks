# Ansible Automation Platform Playbooks

This repository contains playbooks to automate the following tasks on proxmox virtualization:

- Create a RHEL-9 VM template with cloud-init
- Create a VM from RHEl9 template
  - Install the Ansible automation platform using redhat-cop [aap_utilities](https://github.com/redhat-cop/aap_utilities)
- Following Job and Workflow templates are created using [awx](https://docs.ansible.com/ansible/latest/collections/awx/awx/index.html) modules
  - Workflow template
    - Three node OpenShift Cluster
    - Single Node OpenShift Cluster
    - Destroy 3 node cluster
  - Job Templates using surveys and without surveys

## Proxmox

Helper script for fresh proxmox installation

```bash
ssh proxmox
$ bash -c "$(wget -qLO - https://github.com/tteck/Proxmox/raw/main/misc/post-pve-install.sh)"
exit
```

```yaml
ansible-playbook -i inventory playbooks/proxmox/prepare_host.yaml
```

## Prepare, Download & Setup AAP

```yaml
ansible-playbook -i inventory/hosts.yaml playbooks/aap-controller/create.yaml -e "aap_setup_down_offline_token=..."
```

## Configure AAP templates

```yaml
ansible-playbook playbooks/aap-controller/config.yaml
```

## Resources

- Generate offline [token](https://access.redhat.com/articles/3626371)
- [API](https://access.redhat.com/management/api) documentation
