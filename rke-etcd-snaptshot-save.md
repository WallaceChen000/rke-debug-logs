## rke etcd snapshot save  
```sh  
root@ks-9047489:~# rke etcd snapshot-save --config cluster.yml --name etcd-snapshot.3no
INFO[0000] Running RKE version: v1.3.12
INFO[0000] Starting saving snapshot on etcd hosts
INFO[0000] [dialer] Setup tunnel for host [172.27.116.67]
INFO[0000] [dialer] Setup tunnel for host [172.27.116.65]
INFO[0000] [dialer] Setup tunnel for host [172.27.116.66]
INFO[0000] Removing container [cluster-state-deployer] on host [172.27.116.67], try #1
INFO[0000] Removing container [cluster-state-deployer] on host [172.27.116.66], try #1
INFO[0000] Removing container [cluster-state-deployer] on host [172.27.116.65], try #1
INFO[0000] [remove/cluster-state-deployer] Successfully removed container on host [172.27.116.66]
INFO[0000] [state] Deploying state file to [/etc/kubernetes/etcd-snapshot.3no.rkestate] on host [172.27.116.66]
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
INFO[0000] [remove/cluster-state-deployer] Successfully removed container on host [172.27.116.65]
INFO[0000] [state] Deploying state file to [/etc/kubernetes/etcd-snapshot.3no.rkestate] on host [172.27.116.65]
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
INFO[0000] [remove/cluster-state-deployer] Successfully removed container on host [172.27.116.67]
INFO[0000] [state] Deploying state file to [/etc/kubernetes/etcd-snapshot.3no.rkestate] on host [172.27.116.67]
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67]
INFO[0001] Starting container [cluster-state-deployer] on host [172.27.116.66], try #1
INFO[0001] Starting container [cluster-state-deployer] on host [172.27.116.65], try #1
INFO[0001] Starting container [cluster-state-deployer] on host [172.27.116.67], try #1
INFO[0002] [state] Successfully started [cluster-state-deployer] container on host [172.27.116.65]
INFO[0002] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.65]
INFO[0002] Container [cluster-state-deployer] is still running on host [172.27.116.65]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0002] [state] Successfully started [cluster-state-deployer] container on host [172.27.116.66]
INFO[0002] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.66]
INFO[0002] Container [cluster-state-deployer] is still running on host [172.27.116.66]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0002] [state] Successfully started [cluster-state-deployer] container on host [172.27.116.67]
INFO[0003] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.67]
INFO[0003] Container [cluster-state-deployer] is still running on host [172.27.116.67]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0003] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.65]
INFO[0003] Container [cluster-state-deployer] is still running on host [172.27.116.65]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0003] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.66]
INFO[0003] Container [cluster-state-deployer] is still running on host [172.27.116.66]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0004] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.67]
INFO[0004] Container [cluster-state-deployer] is still running on host [172.27.116.67]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0004] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.65]
INFO[0004] Container [cluster-state-deployer] is still running on host [172.27.116.65]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0004] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.66]
INFO[0004] Container [cluster-state-deployer] is still running on host [172.27.116.66]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0005] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.67]
INFO[0005] Container [cluster-state-deployer] is still running on host [172.27.116.67]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0005] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.65]
INFO[0005] Container [cluster-state-deployer] is still running on host [172.27.116.65]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0005] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.66]
INFO[0005] Container [cluster-state-deployer] is still running on host [172.27.116.66]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0006] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.67]
INFO[0006] Container [cluster-state-deployer] is still running on host [172.27.116.67]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0006] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.65]
INFO[0006] Container [cluster-state-deployer] is still running on host [172.27.116.65]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0006] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.66]
INFO[0006] Container [cluster-state-deployer] is still running on host [172.27.116.66]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0007] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.67]
INFO[0007] Container [cluster-state-deployer] is still running on host [172.27.116.67]: stderr: [], stdout: [Waiting for file [/etc/kubernetes/cluster.rkestate] to be successfully copied to this container, retry count 1
]
INFO[0007] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.65]
INFO[0007] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.66]
INFO[0008] Waiting for [cluster-state-deployer] container to exit on host [172.27.116.67]
INFO[0008] Removing container [cluster-state-deployer] on host [172.27.116.65], try #1
INFO[0008] Removing container [cluster-state-deployer] on host [172.27.116.66], try #1
INFO[0008] Removing container [cluster-state-deployer] on host [172.27.116.67], try #1
INFO[0008] [remove/cluster-state-deployer] Successfully removed container on host [172.27.116.65]
INFO[0008] [remove/cluster-state-deployer] Successfully removed container on host [172.27.116.66]
INFO[0009] [remove/cluster-state-deployer] Successfully removed container on host [172.27.116.67]
INFO[0009] [etcd] Running snapshot save once on host [172.27.116.65]
INFO[0009] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
INFO[0009] Starting container [etcd-snapshot-once] on host [172.27.116.65], try #1
INFO[0011] [etcd] Successfully started [etcd-snapshot-once] container on host [172.27.116.65]
INFO[0011] Waiting for [etcd-snapshot-once] container to exit on host [172.27.116.65]
INFO[0011] Container [etcd-snapshot-once] is still running on host [172.27.116.65]: stderr: [time="2023-02-22T10:00:55Z" level=info msg="Initializing Onetime Backup" name=etcd-snapshot.3no
], stdout: []
INFO[0012] Waiting for [etcd-snapshot-once] container to exit on host [172.27.116.65]
INFO[0012] Removing container [etcd-snapshot-once] on host [172.27.116.65], try #1
INFO[0012] [etcd] Running snapshot save once on host [172.27.116.66]
INFO[0012] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
INFO[0013] Starting container [etcd-snapshot-once] on host [172.27.116.66], try #1
INFO[0014] [etcd] Successfully started [etcd-snapshot-once] container on host [172.27.116.66]
INFO[0014] Waiting for [etcd-snapshot-once] container to exit on host [172.27.116.66]
INFO[0015] Removing container [etcd-snapshot-once] on host [172.27.116.66], try #1
INFO[0015] [etcd] Running snapshot save once on host [172.27.116.67]
INFO[0015] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67]
INFO[0016] Starting container [etcd-snapshot-once] on host [172.27.116.67], try #1
INFO[0017] [etcd] Successfully started [etcd-snapshot-once] container on host [172.27.116.67]
INFO[0017] Waiting for [etcd-snapshot-once] container to exit on host [172.27.116.67]
INFO[0018] Removing container [etcd-snapshot-once] on host [172.27.116.67], try #1
INFO[0019] Finished saving/uploading snapshot [etcd-snapshot.3no] on all etcd hosts
root@ks-9047489:~#

root@ks-9047489:~# ls -l /mnt/rancher-cmd-data/opt/rke/etcd-snapshots/
total 253660
...
-rw------- 1 root root   447450 Feb 22 18:00 etcd-snapshot.3no.zip

```  