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

## Meanings of terms:

* **hosts** - This is an ansible term which is ordinarily to define remote hosts to connect to, like webservers and defines details like their IP address and SSH key to use. For us, we always connect via localhost and so the only meaning of this is to define variables at a platform and region scope.
* **groups** - These are groups of hosts, we are using this ansible construct in order to share variables across platforms or everyone
