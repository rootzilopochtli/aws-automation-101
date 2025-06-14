# ansible-aws-apache-lb

Playbooks to create simple instances of aws (Amazon Machine Image [AMI]) with apache and load balancing.

Requirements
------------

+ Steps described in [Amazon Web Services Guide](https://docs.ansible.com/ansible/latest/collections/amazon/aws/docsite/guide_aws.html)

Variables
--------------

You need to modify the playbooks with the corresponding variables of your AWS account.

For storing these in a vars_file, ideally encrypted with ansible-vault:

```
---
aws_access_key: "--REMOVED--"
aws_secret_key: "--REMOVED--"
```

If you store your credentials in vars_file, you need to refer to them in each AWS-module. For example:

```
- amazon.aws.ec2_instance:
    aws_access_key: "{{ aws_access_key }}"
    aws_secret_key: "{{ aws_secret_key }}"
    key_name: "example-ssh-key"
    image_id: "..."
```

Or they can be specified using “module_defaults” at the top of a playbook:

```
- hosts: localhost
  module_defaults:
    group/aws:
      aws_access_key: '{{ aws_access_key }}'
      aws_secret_key: '{{ aws_secret_key }}'
      region: '{{ region }}'
  tasks:
    - amazon.aws.ec2_instance:
        key_name: "example-ssh-key"
        image_id: "..."
```

Dependencies
------------

These playbooks were successfully tested in Fedora 42 with Ansible 2.18 @ 2025.

Example Playbook Run
----------------

You need to run the playbook specifying the private key file to connect to the aws instances:

```
$ ansible-playbook aws-lb-apache.yml --key-file _Your_rsa_private_key_path_
```

Author Information
------------------

This playbooks was created in 2018 and updated in 2025 by [Alex Callejas](https://www.x.com/dark_axl), blog [rootzilopochtli.com](https://www.rootzilopochtli.com/).
