# k8s-vagrant-test-cluster

Test bench for running a kubernetes cluster with multiple virtual machines. Utilizes calico pod network.

## Required programs

- virtualbox
- vagrant

## Useful commands

```bash
# create
vagrant up
# update
vagrant provision
# ssh
vagrant ssh k8s-master
vagrant ssh node-1
vagrant ssh node-2
# in ssh session @ k8s-master
# from this point on, you can deploy whatever you wish into the cluster
kubectl cluster-info
kubectl get nodes
kubectl get pods
kubectl apply -f thing-you-wish-to-create.yml
```

## References

The vagrant/ansible related scripts were adapted from: https://kubernetes.io/blog/2019/03/15/kubernetes-setup-using-ansible-and-vagrant/

I did have to edit the provided ansible commands in order to make this work on Ubuntu 20.04 with the latest version of kubernetes, since that tutorial is from 2019. I also faced some issues, related to changed defaults in kubernetes/kubelet, which I had to resolve by providing "daemon.json" for the docker engine in order to match the defaults.
