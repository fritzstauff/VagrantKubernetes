# Test environment for Kuberenetes 

For now its just a single master node and two workers with Docker and Calico network plugin. Intended for local development. Testing on mac with latest stable reqs. 

## Pre Reqs
* [Install Virtual Box](https://www.virtualbox.org/wiki/Downloads)
* [Install Vagrant](https://www.vagrantup.com/)
* [Install Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
* Install Ansible ```brew install ansible```

## Bring Up Environment
* vagrant up

## Confirm It Works
* ```source env.sh```
* ```kubectl get nodes```
* ```watch kubectl get pods --all-namespaces```

## Access Dashboard
* ```source env.sh```
* ``` kubectl proxy ```
* While kubectl proxy is running goto http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy
* Select token auth and paste in contents of file ``` cat admin_token ```

## Pause Work
* vagrant halt

## Start Work
* vagrant up 
* vagrant ssh
