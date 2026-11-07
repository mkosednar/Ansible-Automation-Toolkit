# Safety and Usage Guidelines

Ansible playbooks can change remote systems. Read this document before running any playbook.

## Before execution

- Read the complete playbook and all referenced variables.
- Confirm the inventory, host pattern, and target count.
- Test against a disposable host or isolated lab first.
- Use `--syntax-check` to catch YAML and playbook syntax issues.
- Use `--check --diff` for supported tasks, but do not treat check mode as a guarantee that no changes will occur.
- Back up important data and configuration before maintenance.
- Run privileged tasks only when required.

## Credentials and secrets

- Never commit passwords, private keys, tokens, or production credentials.
- Use Ansible Vault or an approved secrets manager.
- Keep private inventory files out of version control.
- Apply least-privilege access to automation accounts.

## Change management

- Prefer read-only audit playbooks before remediation.
- Use narrow host patterns and limit scope with `--limit`.
- For disruptive maintenance, use staged rollouts and maintenance windows.
- Review package updates, service restarts, firewall changes, and account changes before approval.
- Keep a recovery path and a known-good backup.

## Platform notes

- Linux tasks may require Python and SSH access on managed hosts.
- Windows tasks require a correctly configured WinRM or PSRP connection and suitable authentication.
- Network automation is vendor- and OS-version-specific. Validate collections, modules, and command syntax against the target platform.

## Disclaimer

These examples are provided as starting points. They are not a substitute for testing, change review, backups, or platform-specific documentation. Use them at your own risk.
