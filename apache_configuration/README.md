# Ansible Playbook: Apache Server Configuration

This Ansible playbook automates the configuration of Apache web servers. It installs Apache packages, starts the Apache service, allows HTTP traffic through the firewall, deploys an index.html file to the web server's document root directory, and restarts the Apache service to apply the changes.

## Prerequisites

1. **Ansible**: Ensure Ansible is installed on your control node from where you'll run this playbook.

## Usage

1. **Inventory Setup**: Make sure your inventory file (`hosts`) includes the target servers where you want to configure Apache servers. Ensure these servers are accessible via SSH.

2. **Edit the Index File**: Place your desired index.html file at the location specified in the playbook (`/tmp/index.html`).

3. **Running the Playbook**:
   ```bash
   ansible-playbook -i <path_to_inventory_file> playbook.yml
Replace <path_to_inventory_file> with the path to your inventory file.

## Playbook Explanation

- **name**: Configuration Apache servers.
- **hosts**: Specifies the target hosts where Apache will be configured. If set to `all`, it targets all hosts defined in the inventory file.
- **tasks**:
  - **Install Apache packages**: Installs the `httpd` package using the `yum` module.
  - **Starting Apache service**: Starts the Apache service using the `service` module.
  - **Add firewall rule to allow HTTP traffic**: Allows HTTP traffic through port 80 using the `firewalld` module.
  - **Reload firewalld**: Reloads the firewalld service to apply the new rule using the `systemd` module.
  - **Copy index file to the Apache servers**: Deploys the index.html file to the web server's document root directory using the `copy` module.
  - **Restarting Apache service after all the required changes**: Restarts the Apache service to apply the configuration changes using the `service` module.

## Contributing

Contributions are welcome! If you encounter any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request.

