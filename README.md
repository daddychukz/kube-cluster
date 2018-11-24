## Deployment of A Two Node and One Master Kubernetes Cluster With Ansible on AWS


## STEPS
- Spin up 3 Ubuntu 18.06 instances on your AWS
- Tag respectively Master, Worker 1, and Worker 2
- Set their respective hostnames in appropriate fields on the `hosts` file
- Generate SSH keys on your local system and register public key on each of the instances.
- You should be able to SSH into each server as the root user with your SSH key pair.
- Test the servers to get response using the command below:
```
ansible all -i hosts -m ping
```
- If successful, run the playbook in this order:
  - ansible-playbook -i hosts initial.yml
  - ansible-playbook -i hosts kube-dependencies.yml
  - ansible-playbook -i hosts deploy_master.yml
  - ansible-playbook -i hosts deploy_workers.yml

## Note:
All commands in this file is assumed to be run in same directory you have these files saved.