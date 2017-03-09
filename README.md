Introduction
===

This project provides a set of examples for managing AWS instances. These
examples were built for the Indianapolis Ansible meetup. If you'd like to test
these examples out on your own, you may want to change the various vars in the
playbooks for your own needs.

Inventory
===

Inventory files are pulled from the contrib/inventory directory in Ansible. In
order to access the specific account, you will need to set three values.

* AWS_ACCESS_KEY_ID # Access key for AWS account
* AWS_SECRET_ACCESS_KEY # Secret key for AWS account
* EC2_REGION # The region where we will deploy our instances

These can be be set in the ec2.ini or in your environment

In order to SSH into the instances, you will need to set your ansible_ssh_user
to the default "maintuser"

Executing a Playbook
===

```
ansible-playbook -i inventory/gce.py playbooks/<playbook_name>
```

Available Playbooks
===
name | description
--- | ---
setup | Creates a set of 3 demo instances
teardown | Cleans everything from the demo up
httpd | Installs apache and a simple index page to each instance
load_balancer | Adds a load balancer in from of our 3 web servers
ami | Creates an image from an instance
snapshot | Snapshots each volume for each instance
