# ansible-vars-demo


## Purpose

Allow the following level of vars, with each one superseding the last in variable precedence:
* **Central variables** shared by all - declared in `group_vars/all`
* **Platform variables** shared by a platform - declared in `group_vars/web` and `group_vars/browse`
* **Region variables** specific to a region, which have optionally been defined for web euw in `host_vars/web-euw.yaml`


## How to run:

Run this ansible command:
```bash
ansible-playbook playbook.yml -l web-euw -e stage=dev
```

* -l: targets your platform and region
* -e stage= targets your stage, dev or prod
