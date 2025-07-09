# Usage

This repository contains an Ansible playbook and a custom role for optimizing Linux system performance.

## Playbook: optimize_linux.yml

- Main playbook to apply system optimizations and invoke the `auto-cpufreq` role.

## Role: auto-cpufreq

- Located in `roles/auto-cpufreq/`
- Contains tasks, variables, and metadata for CPU frequency management.

### Directory Structure

```
roles/
  auto-cpufreq/
    tasks/
      main.yml
    vars/
      main.yml
    defaults/
      main.yml
    meta/
      main.yml
optimize_linux.yml
README.md
```

## How to Run

```sh
ansible-playbook -i <inventory> optimize_linux.yml
```

## Customization

- Edit variables in `roles/auto-cpufreq/vars/main.yml` or `defaults/main.yml` as needed.
- Add more roles or tasks as required for your environment.

# Latitude 5520 Linux Optimization Ansible Playbook

This repository contains an Ansible playbook (`optimize_linux.yml`) designed to optimize and configure a Dell Latitude 5520 running Linux. The playbook automates a variety of system tweaks, package installations, and configuration changes to improve performance, usability, and security.

## Features

The playbook typically performs the following tasks (customize as needed):

- Updates and upgrades system packages
- Installs essential utilities and productivity tools
- Configures power management for laptops
- Applies kernel and system parameter optimizations
- Sets up firewall and security enhancements
- Tweaks GNOME or other desktop environment settings
- Removes unnecessary bloatware
- Configures hardware drivers (Wi-Fi, graphics, etc.)
- Sets up custom scripts or dotfiles

> **Note:** The exact tasks depend on the contents of `optimize_linux.yml`. Review the playbook to see all actions performed.

## Prerequisites

1. **Ansible Installed:**

   - On Ubuntu/Debian: `sudo apt update && sudo apt install ansible`
   - On Fedora: `sudo dnf install ansible`
   - On Arch: `sudo pacman -S ansible`

2. **Sudo Privileges:**

   - You must have sudo access on the target machine(s).

3. **Inventory File:**
   - Create an `inventory` file in the project directory listing the target hosts. For local execution, use:
     ```
     [local]
     localhost ansible_connection=local
     ```

## How to Run the Playbook

1. **Clone the Repository:**

   ```sh
   git clone <this-repo-url>
   cd latitude-5520-opt
   ```

2. **(Optional) Review and Edit the Playbook:**

   - Open `optimize_linux.yml` and adjust tasks as needed for your system.

3. **Create/Edit the Inventory File:**

   - See the example above.

4. **Run the Playbook:**

   ```sh
   ansible-playbook -i inventory optimize_linux.yml
   ```

   - Add `--ask-become-pass` if prompted for a sudo password.

5. **Verify Changes:**
   - Reboot if required and check that all optimizations have been applied.

## Troubleshooting

- If you encounter errors, check the Ansible output for details.
- Ensure all required roles and collections are installed (see `requirements.yml` if present).
- For permission issues, use `--ask-become-pass`.

## Customization

- Modify `optimize_linux.yml` to add or remove tasks as needed.
- Adjust the inventory file to target remote hosts or groups.

## License

This project is open source. See `LICENSE` if present.
