## Objective

This application contains an ansible playbook which will send shutdown command of a linux system and wait for the
system to go offline fully. The list of operations and the supported operating systems are described below.

## Available variables

```yaml
# group_vars/all.yml
---
ping_count: 4
wait_time_before_ping_again: 5
retries: 5
```

Modify them to meet your expectation.

### Task Lists

1. Instruct for shutdown
2. Wait for to go the system oggline fully

### Supported Operating Systems

The solution is tested on Operating Systems,

1. CentOS 7

Tis should work almost on Linux systems.

## Usage

To run the playbook we need to locate the inventory file on which the playbook will perform. The command will look like
below:

```shell
$ ansible-playbook -i <inventory_name> <name_of_playbook>
```

For our case the above command will be translated like this:

```shell
$ ansible-playbook -i hosts system-shutdown-manager.yml
```

where **hosts** is the inventory file and **system-shutdown-manager.yml** is the playbook.

#### Sample `hosts` file

```ini
192.168.1.121
some-machine.com
```

**Note:**

- This solution is specifically created for `root` user to configure the systems. Any `sudo` user other that _root_
should work as expected providing superuser password with `--ask-become-pass` option.

**Tips:**

An example hosts file `hosts.sample` is provided with the solution for the ease of understanding.
