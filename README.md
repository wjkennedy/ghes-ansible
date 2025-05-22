# GitHub Enterprise Upgrade Automation

This repository contains an Ansible playbook for upgrading GitHub Enterprise Server (GHES) over SSH using a `.pem` key.

## Files

- `inventory.ini` — Defines test and prod servers with SSH access.
- `upgrade_ghes.yml` — Ansible playbook to:
  - Set maintenance mode
  - Log current GHES version
  - Download and prep upgrade package
  - Run the upgrade
  - Log all steps
- `README.md` — You're reading it.

## Usage

Ensure your `.pem` key is present and readable at the specified path.

Then run:

```bash
ansible-playbook -i inventory.ini upgrade_ghes.yml
```

Control target host with:

```bash
ansible-playbook -i inventory.ini upgrade_ghes.yml --limit ghes-test
```

Ensure your user has privilege escalation (`sudo`) rights.
