# ansible-gce-apache-lb

Playbooks to create simple instances of gce centos/apache with load balancing

Requirements
------------

+ Steps described in [Google Cloud Platform Guide](http://docs.ansible.com/ansible/latest/scenario_guides/guide_gce.html)

Variables
--------------

You need to modify the playbooks with the corresponding variables of your GCP account:

```
  vars:
    service_account_email: _Your_gce_service_account_email_
    credentials_file: _Your_json_credentials_file_
    project_id: _Your_project_id_


    metadata: '{"sshKeys":" _Your_gce_user:_Your_rsa_public_key_ "}'

    remote_user: _Your_gce_user_

```

Dependencies
------------

These playbooks were successfully tested in Fedora 34 and CentOS 8 Stream with Ansible 2.9 @ 2021.

Example Playbook Run
----------------

You need to run the playbook specifying the private key file to connect to the gce instances:

```
$ ansible-playbook gce-lb-apache.yml --key-file _Your_rsa_private_key_path_
```

License
-------

All parts of this material are made available under the terms of the [MIT License](LICENSE).

Author Information
------------------

This playbooks was created in 2018 and updated in 2021 by [Alex Callejas](https://www.twitter.com/dark_axl), blog [rootzilopochtli.com](https://www.rootzilopochtli.com/).
