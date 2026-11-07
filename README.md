# Ansible Automation Toolkit

A practical collection of Ansible playbooks, roles, and automation examples for Linux and Windows administration, configuration management, security auditing, and network automation.

## Project status

This repository is being built incrementally. The playbooks currently included are starter examples; planned areas are not represented as implemented functionality.

## Current playbooks

| Path | Purpose | Change level |
| --- | --- | --- |
| `01-Linux/linux-inventory.yml` | Collect Linux host facts | Read-only |
| `01-Linux/linux-package-updates.yml` | Update packages on Debian/Ubuntu or RHEL-family hosts | Changes packages |
| `01-Linux/linux-user-management.yml` | Ensure a configurable local account exists | Changes accounts |
| `01-Linux/linux-security-audit.yml` | Report selected SSH and host security settings | Read-only |
| `02-Windows/windows-inventory.yml` | Collect Windows host facts | Read-only |

## Planned areas

- Network device inventory and configuration backups
- Windows maintenance and security auditing
- Docker and application deployment
- Monitoring and certificate audits
- Reusable roles and reporting

These items are planned, not implemented yet.

## Requirements

- Ansible Core (see the official [installation guide](https://docs.ansible.com/projects/ansible/latest/installation_guide/intro_installation.html)).
- SSH access and Python on managed Linux hosts.
- Windows management configured using a supported connection method such as WinRM or PSRP.
- Collections listed in `requirements.yml` where applicable.

## Quick start

1. Install Ansible on the control node.
2. Copy `inventories/hosts.example.ini` to a private inventory file and replace the example hosts.
3. Review the selected playbook and its variables.
4. Start with a read-only playbook:

   ```bash
   ansible-playbook -i inventories/hosts.example.ini 01-Linux/linux-inventory.yml
   ```

5. For changing playbooks, first use `--check --diff` where supported and target a test host.

Do not put passwords, private keys, API tokens, or production inventory data in this repository. Use Ansible Vault or an approved secrets manager.

## Safety

Read [docs/SAFETY.md](docs/SAFETY.md) before running playbooks. A playbook can make real changes to every host matched by its inventory and patterns. Check mode is useful but is not a perfect simulation.

## Compatibility and testing

Examples are written for current Ansible conventions, but have not yet been executed against real Linux or Windows hosts or validated across all supported distributions. Review module requirements and test in a disposable environment before production use.

## License

No license has been selected yet. All rights reserved by default; do not assume the contents may be redistributed or reused until a license is added.
