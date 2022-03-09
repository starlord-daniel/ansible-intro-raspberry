# Raspberry Pi Ansible demo

A simple demo Ansible project as a starting point to configure your Raspberry PI.

Run the playbook with: `ansible-playbook playbook.yml -i ansible_hosts`

## Folder Structure

```bash
├── ansible_hosts
├── playbook.yml
└── roles
    └── raspberry_basic_setup
        ├── README.md
        ├── defaults
        │   └── main.yml
        ├── tasks
        │   ├── install_dependencies.yml
        │   ├── main.yml
        │   └── uninstall_dependencies.yml
        ├── templates
        │   └── README.j2
        └── vars
            └── main.yml
```

## Objective

1. Structure of Ansible Playbook
    - Becoming
    - Roles
    - Variables
    - Hosts file
1. Structure of Ansible Role
    - Start with tasks -> main.yml
    - Explain include_tasks
    - Explain install_dependencies.yml and the state: present and absent
    - Go into template and template task
1. Demonstration
    - Run `ansible-playbook playbook.yml -i ansible_hosts`
    - Template gets copied and replaced
    - Tools get installed
    - Tools get uninstalled
    - Variables get replaced (show 2 versions of this) - `ansible-playbook playbook.yml -i ansible_hosts --extra-vars "destination_directory=another_project application_name: an even greater app"`
    - Disable Cowsay (for the boring people) with: export ANSIBLE_NOCOWS=1 (enable with 0)
    - Testing and Verbose output with -v

## Links

- [General Ansible Documentation](https://docs.ansible.com/)
- [Most important for tasks: ansible.builtin](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/index.html)
- [Great for working with Azure: Azure.AzCollection](https://docs.ansible.com/ansible/latest/collections/azure/azcollection/index.html#plugins-in-azure-azcollection)
