EC2 Group Info
==============

![Ansible Lint](https://github.com/matcra587/ansible-role-ec2-sgi/workflows/Ansible%20Lint/badge.svg)
![Molecule Test](https://github.com/matcra587/ansible-role-ec2-sgi/workflows/Molecule%20Test/badge.svg)

A role to gather information about EC2 security groups in AWS.

Requirements
------------

The below requirements are needed on the host that executes Ansible.

* boto
* boto3
* python >= 2.6

Role Variables
--------------

| Variable | Type | Default Value |
| :--- | :--- | --- |
| `aws_access_key` | string | *omit* |
| `aws_region` | string | eu-west-1 |
| `aws_secret_key` | string | *omit* |
| `aws_security_token` | string | *omit* |
| `ec2_vpc_id` | string / list | *omit* |
| `sg_group_name` | string / list | *omit* |
| `sg_group_id` | string / list | *omit* |
| `sg_owner_id` | string / list | *omit* |
| `sg_tag_name` | string / list | *omit* |
| `show_output` | boolean | false |

Valid AWS credentials **must** be specified either by setting `aws_access_key` and `aws_secret_key` variables or by defining `AWS_ACCESS_KEY` and `AWS_SECRET_KEY` environment variables.

Dependencies
------------

N/A

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - name: Gather Facts about all Security Groups
      hosts: localhost
      connection: local
      roles:
         - role: ansible-role-ec2-sgi

    - name: Gather Facts about all Security Groups and show output
      hosts: localhost
      connection: local
      roles:
         - role: ansible-role-ec2-sgi
           show_output: true

    - name: Gather Facts about all Security Groups in a particular VPC
      hosts: localhost
      connection: local
      roles:
         - role: ansible-role-ec2-sgi
           ec2_vpc_id: 89056340234

License
-------

[MIT](LICENSE)

Author Information
------------------

Matt Craven
