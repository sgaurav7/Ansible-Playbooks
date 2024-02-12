# Ansible Playbook: Linux Server Package Installation

This Ansible playbook automates the installation of specified packages on Linux servers. It utilizes the `yum` package manager to ensure the desired packages are present.

## Prerequisites

1. **Ansible**: Ensure Ansible is installed on your control node from where you'll run this playbook.

## Usage

1. **Inventory Setup**: Make sure your inventory file (`hosts`) includes the target servers where you want to install the packages. Ensure these servers are accessible via SSH.

2. **Edit Variables**: Modify the `pkg_name` variable in the playbook according to your requirements. Add or remove packages as needed.

3. **Running the Playbook**:
   ```bash
   ansible-playbook -i <path_to_inventory_file> playbook.yml

Replace <path_to_inventory_file> with the path to your inventory file.

## Playbook Explanation

- **name**: Playbook for the installation of packages on the Linux server.
- **hosts**: Specify the target hosts or host group where the packages will be installed. If set to `all`, it targets all hosts defined in the inventory file.
- **vars**: Defines the `pkg_name` variable which lists the packages to be installed.
- **tasks**:
  - **name**: Install the package.
  - **yum**: Ansible module used for package management on CentOS/RHEL-based systems.
    - **name**: Specifies the list of packages to be installed, taken from the `pkg_name` variable.
    - **state**: Ensures that the packages are present on the system (`present`).

## Contributing

Contributions are welcome! If you encounter any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request.
