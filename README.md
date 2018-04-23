# Ansible Taskid Patch for ara
Using custom taskid to trace playbook report generate by ara

## How to PATCH
```sh
$ git clone https://github.com/allanhung/ansible_taskid.git
$ export ARA_LOCATION=$(python -c "import os,ara; print(os.path.dirname(ara.__file__))")
$ cd $ARA_LOCATION && patch -p1 < ansible_taskid/ara_playbook_id.patch

$ export ANSIBLE_LOCATION=$(python -c "import os,ansible; print(os.path.dirname(ansible.__file__))")
$ cd $ANSIBLE_LOCATION && patch -p1 < ansible_taskid/ansible_taskid.patch
```
