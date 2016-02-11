python-latest
=============

Ansible role to install the latest **Python 3** version in **Ubuntu** using the [deadsnakes] ppa.

Ubuntu ships Python 3 [separately from v2], which is the default. Python 3 versions in Ubuntu LTS releases are:

- 10.04: v3.1
- 12.04: v3.2
- 14.04: v3.4

Add the role `python-latest` to [install Python 3.5].

Variables
---------

- `python_version`: The python version to install (major.minor), default: 3.5

Playbook examples
-----------------

Plain:

    ---
    # Install the latest Python 3 version
    - hosts: servers
      roles:
        - python-latest

Specify variables:

    ---
    # specify extra variable ``-e "host=xyz"``
    - hosts: "{{ host | default('localhost') }}"
      gather_facts: no
      roles:
        - role: python-latest
          python_version: 3.4

[deadsnakes]: https://launchpad.net/~fkrull/+archive/ubuntu/deadsnakes
[separately from v2]: http://askubuntu.com/questions/134747/how-do-i-run-python-3
[install Python 3.5]: http://askubuntu.com/a/290283/233134
