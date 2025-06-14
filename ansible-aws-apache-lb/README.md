# ansible-aws-apache-lb

Playbooks to create simple instances of aws (centos, fedora or rhel) with apache and load balancing

Requirements
------------

+ Steps described in [Google Cloud Platform Guide](http://docs.ansible.com/ansible/latest/scenario_guides/guide_gce.html)

Variables
--------------

You need to modify the playbooks with the corresponding variables of your AWS account:

```
  vars:
    service_account_email: _Your_aws
    credentials_file: _Your_json_credentials_file_
    project_id: _Your_project_id_


    metadata: '{"sshKeys":" _Your_gce_user:_Your_rsa_public_key_ "}'

    remote_user: _Your_aws_user_

```

Dependencies
------------

These playbooks were successfully tested in Fedora 42 with Ansible 2.18 @ 2025.

Example Playbook Run
----------------

You need to run the playbook specifying the private key file to connect to the gce instances:

```
$ ansible-playbook aws-lb-apache.yml --key-file _Your_rsa_private_key_path_
```

Author Information
------------------

This playbooks was created in 2018 and updated in 2025 by [Alex Callejas](https://www.x.com/dark_axl), blog [rootzilopochtli.com](https://www.rootzilopochtli.com/).
