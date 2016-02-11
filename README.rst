=============
python-latest
=============

Installs the latest **Python 3** version in **Ubuntu** using the deadsnakes_ ppa.

Ubuntu ships Python 3 `separately from v2`_, which is the default. Python 3 versions in Ubuntu LTS releases are:

- 10.04: v3.1
- 12.04: v3.2
- 14.04: v3.4

Please also note that Django requires for Python 3 min v3.4.
Add the role ``python_latest`` to `install Python 3.5`_.

Variables
---------

- ``python_version``: The python version to install (major.minor), default: 3.5

Playbook examples
-----------------

Plain::

    ---
    # Install the latest Python 3 version
    - hosts: servers
      roles:
        - python_latest

Specify variables::

    ---
    # specify extra variable ``-e "host=xyz"``
    - hosts: "{{ host | default('localhost') }}"
      gather_facts: no
      roles:
        - role: python_latest
          python_version: 3.4

.. _deadsnakes: https://launchpad.net/~fkrull/+archive/ubuntu/deadsnakes
.. _separately from v2: http://askubuntu.com/questions/134747/how-do-i-run-python-3
.. _install Python 3.5: http://askubuntu.com/a/290283/233134
