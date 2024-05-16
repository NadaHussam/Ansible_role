# Ansible_role

## Description
This Ansible role provides custom configurations and tasks for managing some services.

## Role Structure
The role directory structure follows Ansible best practices:

- `files/`: Contains files to be copied to the target hosts.
- `handlers/`: Defines handlers that can be triggered by tasks.
- `tasks/`: Contains the main tasks for this role.
- `templates/`: Includes Jinja2 templates for generating dynamic files.
- `vars/`: Stores variables specific to this role.
- `inventory/`: Lists the target hosts or groups.
- `ansible.cfg`: Role-specific Ansible configuration.
- `playbook.yml`: playbook that uses this role.

## Hierarchy of ansible-role files
![image](https://github.com/NadaHussam/Ansible_role/assets/165591480/eb282f87-0fdd-4ef5-8d71-cb2e8d5a6a31)

## Usage
1. Install Ansible and dependencies (if not already done).
2. Clone this repository and include the role in your playbook.
3. Customize variables in `vars/main.yml`.
4. Run your playbook using `ansible-playbook playbook.yml --ask-vault-pass`.
5. Will ask you about 2 passwords, Become and Vault.

![Ansible_role_run](https://github.com/NadaHussam/Ansible_role/assets/165591480/6b77600b-05dc-4e38-9e61-5ba3db3eb5e0)

## Encrypting Sensitive Data
To encrypt sensitive data (such as passwords), follow these steps:

1. **Encrypt a File with Ansible Vault**:
   - Use the following command to encrypt the `password.yml` file:
     ```
     ansible-vault encrypt ./roles/web/files/password.yml
     ```
   - This will prompt you for a vault password. Choose a strong password and keep it secure.

2. **Access the Encrypted Content**:
   - The encrypted content in `password.yml` will include the `!vault` tag.
   - You can reference this encrypted content in your tasks or templates.

3. **View Template Output**:
   - To see the output of your `index.html.j2` template, use the following command:
     ```
     curl 172.17.0.2
     ```
   - Replace `172.17.0.2` with the actual IP address or hostname of your target host.
  
![image](https://github.com/NadaHussam/Ansible_role/assets/165591480/57dc5831-f9ab-464c-bc27-88e758028afe)


