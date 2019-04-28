# Setup

Get image: ubuntu image is here
http://cdimage.ubuntu.com/releases/18.04/release/

Touch an empty `ssh` file in the root of the sdcard

Update hostname:
`hostnamectl set-hostname hydra-node3`

Generate ssh key pair:
`ssh-keygen -t rsa -b 4096 -C "ubuntu@hydra-node3"`

`cat ~/.ssh/id_rsa >> ~/.ssh/authorized_hosts`

Reduce gpu memory by adding to `/boot/firmware/config.txt`:
```
gpu_mem=16
```

Enable CPU and Memory Cgroups by adding to `/boot/firmware/cmdline.txt`:
```
cgroup_enable=cpuset cgroup_enable=memory cgroup_memory=1
```
