# Ansible Playbook: Notification Sender

This Ansible playbook facilitates sending notifications to users logged in to specified servers. It utilizes the `wall` command to broadcast a message to all users.

## Prerequisites

1. **Ansible**: Ensure Ansible is installed on your control node from where you'll run this playbook.

## Usage

1. **Inventory Setup**: Make sure your inventory file (`hosts`) includes the target servers where you want to send notifications. Ensure these servers are accessible via SSH.

2. **Edit Variables**: Modify the `salutation` variable in the playbook according to the message you want to send.

3. **Running the Playbook**:
   ```bash
   ansible-playbook -i <path_to_inventory_file> playbook.yml
Replace <path_to_inventory_file> with the path to your inventory file.

## Playbook Explanation

- **name**: Playbook to send notifications.
- **hosts**: Specifies the target hosts where notifications will be sent. If set to `all`, it targets all hosts defined in the inventory file.
- **vars**: Defines the `salutation` variable which contains the message to be broadcasted.
- **tasks**:
  - **name**: Sending notification to the users logged in to the servers.
  - **command**: Executes the `wall` command to broadcast the message specified in the `salutation` variable.

## Contributing

Contributions are welcome! If you encounter any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request.
