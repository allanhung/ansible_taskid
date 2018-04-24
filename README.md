# Ansible Taskid Patch for ara
Using custom taskid to trace playbook report generate by ara

## How to PATCH
```sh
git clone https://github.com/allanhung/ansible_taskid.git
export PATCH_LOCATION=$PWD/ansible_taskid
export ARA_LOCATION=$(python -c "import os,ara; print(os.path.dirname(ara.__file__))")
export ANSIBLE_LOCATION=$(python -c "import os,ansible; print(os.path.dirname(ansible.__file__))")
cd $ARA_LOCATION && patch -p1 < $PATCH_LOCATION/ara_playbook_id.patch
cd $ANSIBLE_LOCATION && patch -p1 < $PATCH_LOCATION/ansible_taskid.patch
```

## Others
Patch is base on ansible 2.5.1 and ara 0.14.6
