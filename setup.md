# Setup

Get image: ubuntu image is here
http://cdimage.ubuntu.com/releases/18.04/release/

Touch an empty `ssh` file in the root of the sdcard

Update hostname:
`hostnamectl set-hostname hydra-node3`

Copy ssh key to authorized keys

Reduce gpu memory by adding to `/boot/firmware/config.txt` (unfortuately it's impossible to take all memory away from the GPU,
16M is as low as it can go):
```
gpu_mem=16
```

Enable CPU and Memory Cgroups by adding to `/boot/firmware/cmdline.txt`:
```
cgroup_enable=cpuset cgroup_enable=memory cgroup_memory=1
```
