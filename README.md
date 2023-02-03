# Setup Fedora Workstation

This Ansible playbook will set up a basic Fedora workstation with the packages and configs that I need.

__NOTE:__ This has only been tested against Fedora Workstation 37

__NOTE:__ This playbook is configured to run against the local host only.

## Table of Contents
  * [Requirements](#requirements)
  * [Bootstrapping](#bootstrapping)
  * [Usage](#usage)

<a name="requirements"></a>
## Requirements

  * [Ansible Control System Requirements](https://docs.ansible.com/ansible/latest/intro_installation.html#control-machine-requirements)
  * A Fedora system with the `ansible` and `git` packages installed.
  * Sudo permissions to run this playbook locally

<a name="bootstrapping"></a>
## Bootstrapping

1. In order to run this playbook, Ansible needs to be installed from the package repos:

```bash
sudo dnf install ansible
```

2. On your local system with ansible and git installed, clone this git repo.

<a name="usage"></a>
## Usage

First, take a look at the [setup-workstation.yml](setup-workstation.yml) file. This file contains all of the options for this playbook. Pick and choose the things that you would like to enable before running the playbook. Most options are a simple "True" or "False" selection.

1. It's a good idea to run a dry-run check before you actually run the playbook to make changes to your system. To perform a dry-run, run the following command:

```bash
ansible-playbook setup-workstation.yml --check
```

__NOTE:__ You will be asked for your your sudo password since this playbook needs root privileges for various tasks.

2. If there are no failures and you want to run it for real, just remove the `--check` from the end of the command:

```bash
ansible-playbook setup-workstation.yml
```

3. For verbose output, you can add up to 4 v's to the end of the command, like so:

```bash
ansible-playbook setup-workstation.yml -vvvv
````