# Ansible Automation Deployment

1. Upload RHEL ISO

    ```bash
    ansible-playbook -i inventory/hosts.yaml playbooks/proxmox/upload-iso.yaml --extra-vars iso_url=""
    ```

2. Create a VM in Proxmox using RHEL ISO

    ```bash
    ansible-playbook -i inventory/hosts.yaml playbooks/proxmox/create-vm.yaml --extra-vars @vars/aap-controller.yaml
    ```

3. Start and complete RHEL installation

4. Setup RHEL to run AAP installer

    ```bash
    ansible-playbook -i inventory/hosts.yaml playbooks/aap-controller/setup.yaml
    ```

5. Run AAP installer

    ```bash
    sudo ./setup.sh
    ```

6. Login into AAP

7. Add quay and vault credentials

8. Add custom execution image from quay

9. Add new project from git repo and select custom execution image

10. Add inventory and choose sourced from project
