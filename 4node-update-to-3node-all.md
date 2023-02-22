There is one cluster consist of 4 nodes.  
+ ks-9047489 (172.27.116.65/172.27.116.55) (etcd, controlplane, worker)  
+ ks-9047366 (172.27.116.66/172.27.116.56) (etcd, controlplane, worker)  
+ ks-9047368 (172.27.116.67/172.27.116.57) (etcd, controlplane, worker)  
+ ks-9047988 (172.27.116.68/172.27.116.58) (etcd, controlplane, worker)  

Use rke tool to update(remove) ks-9047988 node role out of cluster.  
```sh  
root@ks-9047489:~# rke --debug up
DEBU[0000] Loglevel set to [debug]
INFO[0000] Running RKE version: v1.3.12
DEBU[0000] audit log policy found in cluster.yml
INFO[0000] Initiating Kubernetes cluster
DEBU[0000] Loading data.json from local source
DEBU[0000] data.json SHA256 checksum: d5dc093ad17db792ce7b091e490e05fd452597b9fc778b615300554df88d631f
DEBU[0000] Checking if cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0000] Cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0000] Enabling kube-api audit log for cluster version [v1.22.10-rancher1-1]
DEBU[0000] No input provided for maxUnavailableWorker, setting it to default value of 10 percent
DEBU[0000] No input provided for maxUnavailableControlplane, setting it to default value of 1
DEBU[0000] Checking network mode for ingress for cluster version [v1.22.10-rancher1-1]
DEBU[0000] Cluster version [v1.22.10-rancher1-1] needs to have ingress network mode set to hostPort
DEBU[0000] Checking ingress default backend for cluster version [v1.22.10-rancher1-1]
DEBU[0000] Cluster version [v1.22.10-rancher1-1] needs to have ingress default backend disabled
DEBU[0000] Host: 172.27.116.65 has role: etcd
DEBU[0000] Host: 172.27.116.65 has role: controlplane
DEBU[0000] Host: 172.27.116.65 has role: worker
DEBU[0000] Host: 172.27.116.66 has role: etcd
DEBU[0000] Host: 172.27.116.66 has role: controlplane
DEBU[0000] Host: 172.27.116.66 has role: worker
DEBU[0000] Host: 172.27.116.67 has role: etcd
DEBU[0000] Host: 172.27.116.67 has role: controlplane
DEBU[0000] Host: 172.27.116.67 has role: worker
DEBU[0000] [state] previous state found, this is not a legacy cluster
INFO[0000] [certificates] GenerateServingCertificate is disabled, checking if there are unused kubelet certificates
INFO[0000] [certificates] Generating Kubernetes API server certificates
INFO[0000] [certificates] Generating admin certificates and kubeconfig
INFO[0000] [certificates] Generating kube-etcd-172-27-116-55 certificate and key
INFO[0000] [certificates] Generating kube-etcd-172-27-116-56 certificate and key
INFO[0000] [certificates] Generating kube-etcd-172-27-116-57 certificate and key
INFO[0000] [certificates] Deleting unused certificate: kube-etcd-172-27-116-58
INFO[0000] Successfully Deployed state file at [./cluster.rkestate]
DEBU[0000] Checking if cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0000] Cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0000] Enabling kube-api audit log for cluster version [v1.22.10-rancher1-1]
DEBU[0000] Host: 172.27.116.65 has role: etcd
DEBU[0000] Host: 172.27.116.65 has role: controlplane
DEBU[0000] Host: 172.27.116.65 has role: worker
DEBU[0000] Host: 172.27.116.66 has role: etcd
DEBU[0000] Host: 172.27.116.66 has role: controlplane
DEBU[0000] Host: 172.27.116.66 has role: worker
DEBU[0000] Host: 172.27.116.67 has role: etcd
DEBU[0000] Host: 172.27.116.67 has role: controlplane
DEBU[0000] Host: 172.27.116.67 has role: worker
INFO[0000] Building Kubernetes cluster
INFO[0000] [dialer] Setup tunnel for host [172.27.116.65]
INFO[0000] [dialer] Setup tunnel for host [172.27.116.66]
INFO[0000] [dialer] Setup tunnel for host [172.27.116.67]
DEBU[0000] Connecting to Docker API for host [172.27.116.65]
DEBU[0000] Connecting to Docker API for host [172.27.116.67]
DEBU[0000] Connecting to Docker API for host [172.27.116.66]
DEBU[0000] Docker Info found for host [172.27.116.66]: types.Info{ID:"7T67:DXEC:PYY6:VISK:5RG4:M2UV:N6NE:MAI4:QNBJ:PXN6:JNZ3:E6XT", Containers:43, ContainersRunning:41, ContainersPaused:0, ContainersStopped:2, Images:43, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:156, OomKillDisable:true, NGoroutines:138, SystemTime:"2023-02-22T15:40:14.343960758+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc0007280e0), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047366", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
DEBU[0000] Docker Info found for host [172.27.116.67]: types.Info{ID:"VN5L:TH7K:7SRQ:LLCZ:F7QU:TJUR:7AZ7:ETFA:NIKN:KE4N:OEJE:KWUZ", Containers:47, ContainersRunning:42, ContainersPaused:0, ContainersStopped:5, Images:31, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:175, OomKillDisable:true, NGoroutines:153, SystemTime:"2023-02-22T15:40:15.194781754+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc000728310), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047368", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
DEBU[0000] Docker Info found for host [172.27.116.65]: types.Info{ID:"PXEX:4WFR:EIA2:YQWO:7QYJ:AV77:D5FS:5CXU:O7VZ:7V3L:V24Y:IHH2", Containers:136, ContainersRunning:97, ContainersPaused:0, ContainersStopped:39, Images:46, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:459, OomKillDisable:true, NGoroutines:361, SystemTime:"2023-02-22T15:40:14.792743649+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc000728460), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047489", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
DEBU[0000] Checking if cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0000] Cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0000] Enabling kube-api audit log for cluster version [v1.22.10-rancher1-1]
DEBU[0000] Host: 172.27.116.65 has role: etcd
DEBU[0000] Host: 172.27.116.65 has role: controlplane
DEBU[0000] Host: 172.27.116.65 has role: worker
DEBU[0000] Host: 172.27.116.66 has role: etcd
DEBU[0000] Host: 172.27.116.66 has role: controlplane
DEBU[0000] Host: 172.27.116.66 has role: worker
DEBU[0000] Host: 172.27.116.67 has role: etcd
DEBU[0000] Host: 172.27.116.67 has role: controlplane
DEBU[0000] Host: 172.27.116.67 has role: worker
DEBU[0000] Host: 172.27.116.68 has role: etcd
DEBU[0000] Host: 172.27.116.68 has role: controlplane
DEBU[0000] Host: 172.27.116.68 has role: worker
INFO[0000] [network] No hosts added existing cluster, skipping port check
DEBU[0000] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0000] [certificates] kube-apiserver certificate changed, force deploying certs
INFO[0000] [certificates] Deploying kubernetes certificates to Cluster nodes
INFO[0000] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
INFO[0000] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0000] Checking if container [cert-deployer] is running on host [172.27.116.67], try #1
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
DEBU[0000] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67], try #1
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67]
DEBU[0000] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
DEBU[0000] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0001] Starting container [cert-deployer] on host [172.27.116.66], try #1
INFO[0001] Starting container [cert-deployer] on host [172.27.116.67], try #1
DEBU[0003] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0003] Checking if container [cert-deployer] is running on host [172.27.116.67], try #1
DEBU[0003] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0003] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
INFO[0004] Starting container [cert-deployer] on host [172.27.116.65], try #1
DEBU[0006] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0006] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0008] Checking if container [cert-deployer] is running on host [172.27.116.67], try #1
INFO[0008] Removing container [cert-deployer] on host [172.27.116.67], try #1
INFO[0008] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
INFO[0008] Removing container [cert-deployer] on host [172.27.116.66], try #1
INFO[0011] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0011] Removing container [cert-deployer] on host [172.27.116.65], try #1
INFO[0013] [reconcile] Rebuilding and updating local kube config
DEBU[0013] [reconcile] Rebuilding and updating local kube config, creating new kubeconfig
DEBU[0013] Deploying admin Kubeconfig locally at [./kube_config_cluster.yml]
INFO[0013] Successfully Deployed local admin kubeconfig at [./kube_config_cluster.yml]
DEBU[0013] [version] Using ./kube_config_cluster.yml to connect to Kubernetes cluster..
DEBU[0013] [version] Getting Kubernetes server version..
INFO[0013] [reconcile] host [172.27.116.65] is a control plane node with reachable Kubernetes API endpoint in the cluster
INFO[0013] [certificates] Successfully deployed kubernetes certificates to Cluster nodes
INFO[0013] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.65]
DEBU[0013] [remove/file-deployer] Checking if container is running on host [172.27.116.65]
DEBU[0013] [remove/file-deployer] Container doesn't exist on host [172.27.116.65]
DEBU[0013] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0013] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0013] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0016] Starting container [file-deployer] on host [172.27.116.65], try #1
INFO[0018] Successfully started [file-deployer] container on host [172.27.116.65]
INFO[0018] Waiting for [file-deployer] container to exit on host [172.27.116.65]
INFO[0018] Waiting for [file-deployer] container to exit on host [172.27.116.65]
DEBU[0019] Exit code for [file-deployer] container on host [172.27.116.65] is [0]
DEBU[0019] [remove/file-deployer] Checking if container is running on host [172.27.116.65]
DEBU[0019] [remove/file-deployer] Removing container on host [172.27.116.65]
INFO[0019] Removing container [file-deployer] on host [172.27.116.65], try #1
INFO[0020] [remove/file-deployer] Successfully removed container on host [172.27.116.65]
DEBU[0020] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.65]
INFO[0020] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.66]
DEBU[0020] [remove/file-deployer] Checking if container is running on host [172.27.116.66]
DEBU[0020] [remove/file-deployer] Container doesn't exist on host [172.27.116.66]
DEBU[0020] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0020] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0020] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0021] Starting container [file-deployer] on host [172.27.116.66], try #1
INFO[0023] Successfully started [file-deployer] container on host [172.27.116.66]
INFO[0023] Waiting for [file-deployer] container to exit on host [172.27.116.66]
INFO[0023] Waiting for [file-deployer] container to exit on host [172.27.116.66]
DEBU[0025] Exit code for [file-deployer] container on host [172.27.116.66] is [0]
DEBU[0025] [remove/file-deployer] Checking if container is running on host [172.27.116.66]
DEBU[0025] [remove/file-deployer] Removing container on host [172.27.116.66]
INFO[0025] Removing container [file-deployer] on host [172.27.116.66], try #1
INFO[0025] [remove/file-deployer] Successfully removed container on host [172.27.116.66]
DEBU[0025] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.66]
INFO[0025] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.67]
DEBU[0025] [remove/file-deployer] Checking if container is running on host [172.27.116.67]
DEBU[0025] [remove/file-deployer] Container doesn't exist on host [172.27.116.67]
DEBU[0025] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0025] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0025] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0026] Starting container [file-deployer] on host [172.27.116.67], try #1
INFO[0028] Successfully started [file-deployer] container on host [172.27.116.67]
INFO[0028] Waiting for [file-deployer] container to exit on host [172.27.116.67]
INFO[0028] Waiting for [file-deployer] container to exit on host [172.27.116.67]
DEBU[0030] Exit code for [file-deployer] container on host [172.27.116.67] is [0]
DEBU[0030] [remove/file-deployer] Checking if container is running on host [172.27.116.67]
DEBU[0030] [remove/file-deployer] Removing container on host [172.27.116.67]
INFO[0030] Removing container [file-deployer] on host [172.27.116.67], try #1
INFO[0031] [remove/file-deployer] Successfully removed container on host [172.27.116.67]
DEBU[0031] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.67]
INFO[0031] [/etc/kubernetes/audit-policy.yaml] Successfully deployed audit policy file to Cluster control nodes
INFO[0031] [reconcile] Reconciling cluster state
INFO[0031] [reconcile] Check etcd hosts to be deleted
DEBU[0031] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0031] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0031] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0031] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0031] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0031] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0031] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0031] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0031] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0031] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0031] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0031] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0031] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0031] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0031] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0031] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0031] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0031] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0031] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0031] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0031] [remove/etcd] Removing member [etcd-ks-9047988] from etcd cluster
INFO[0031] [remove/etcd] Checking etcd cluster health on [etcd-ks-9047489] after removing [etcd-ks-9047988]
DEBU[0031] [remove/etcd] healthCheckURL for checking etcd cluster health on [etcd-ks-9047489] after removing [ks-9047988]: [https://172.27.116.55:2379/health]
DEBU[0031] [etcd] check etcd cluster health on host [172.27.116.65]
INFO[0036] [etcd] etcd host [172.27.116.65] reported healthy=false
INFO[0041] [etcd] etcd host [172.27.116.65] reported healthy=true
INFO[0041] [remove/etcd] etcd cluster health is healthy on [etcd-ks-9047489] after removing [etcd-ks-9047988]
DEBU[0041] Total time between etcd member deleted and etcd cluster healthy is: [10.094413862s]
INFO[0041] [remove/etcd] Successfully removed member [etcd-ks-9047988] from etcd cluster
INFO[0041] [hosts] host [172.27.116.68] has another role, skipping delete from kubernetes cluster
INFO[0041] [dialer] Setup tunnel for host [172.27.116.68]
DEBU[0041] Connecting to Docker API for host [172.27.116.68]
DEBU[0041] Docker Info found for host [172.27.116.68]: types.Info{ID:"MXKP:YT7W:POR5:IYHK:3IPJ:MTDH:K2AG:IP7X:6M66:73HM:XICA:XUTP", Containers:76, ContainersRunning:46, ContainersPaused:0, ContainersStopped:30, Images:32, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:271, OomKillDisable:true, NGoroutines:222, SystemTime:"2023-02-22T15:40:55.533077195+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc00071c620), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047988", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
INFO[0041] [etcd] Tearing down etcd plane..
DEBU[0041] [remove/etcd] Checking if container is running on host [172.27.116.68]
DEBU[0041] [remove/etcd] Removing container on host [172.27.116.68]
INFO[0041] Removing container [etcd] on host [172.27.116.68], try #1
INFO[0042] [remove/etcd] Successfully removed container on host [172.27.116.68]
DEBU[0042] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.68]
DEBU[0042] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.68]
INFO[0042] Removing container [etcd-rolling-snapshots] on host [172.27.116.68], try #1
INFO[0047] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.68]
INFO[0047] [etcd] Successfully tore down etcd plane..
INFO[0047] [hosts] Host [172.27.116.68] is already a worker or control host, skipping cleanup certs.
INFO[0047] [hosts] Cleaning up host [172.27.116.68]
DEBU[0047] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0047] [hosts] Running cleaner container on host [172.27.116.68]
DEBU[0047] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0047] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0048] Starting container [kube-cleaner] on host [172.27.116.68], try #1
INFO[0051] [kube-cleaner] Successfully started [kube-cleaner] container on host [172.27.116.68]
INFO[0051] Waiting for [kube-cleaner] container to exit on host [172.27.116.68]
DEBU[0052] Exit code for [kube-cleaner] container on host [172.27.116.68] is [0]
INFO[0052] [hosts] Removing cleaner container on host [172.27.116.68]
INFO[0052] Removing container [kube-cleaner] on host [172.27.116.68], try #1
INFO[0053] [hosts] Removing dead container logs on host [172.27.116.68]
DEBU[0053] [cleanup] Starting log link cleanup on host [172.27.116.68]
DEBU[0053] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.68]
DEBU[0053] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.68]
DEBU[0053] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0053] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0055] Starting container [rke-log-cleaner] on host [172.27.116.68], try #1
INFO[0057] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.68]
DEBU[0057] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.68]
DEBU[0058] [remove/rke-log-cleaner] Removing container on host [172.27.116.68]
INFO[0058] Removing container [rke-log-cleaner] on host [172.27.116.68], try #1
INFO[0059] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.68]
DEBU[0059] [cleanup] Successfully cleaned up log links on host [172.27.116.68]
INFO[0059] [hosts] Successfully cleaned up host [172.27.116.68]
INFO[0059] [reconcile] Check etcd hosts to be added
DEBU[0059] [reconcile] Check worker hosts to be deleted
INFO[0059] [hosts] host [172.27.116.68] has another role, skipping delete from kubernetes cluster
INFO[0059] [worker] Tearing down Worker Plane..
INFO[0059] [worker] Host [172.27.116.68] is already a controlplane host, nothing to do.
INFO[0059] [worker] Successfully tore down Worker Plane..
INFO[0059] [hosts] Host [172.27.116.68] is already a controlplane or etcd host, skipping cleanup.
DEBU[0059] [reconcile] Check Control plane hosts to be deleted
INFO[0059] [hosts] Cordoning host [172.27.116.68]
DEBU[0059] Checking node list for node [ks-9047988], try #1
DEBU[0059] Checking node list for node [ks-9047988], try #1
DEBU[0059] Checking node list for node [ks-9047988], try #1
DEBU[0059] Node ks-9047988 is already cordoned: true
INFO[0059] [hosts] Deleting host [172.27.116.68] from the cluster
INFO[0059] [hosts] Successfully deleted host [172.27.116.68] from the cluster
INFO[0059] [controlplane] Tearing down the Controller Plane..
DEBU[0059] [remove/kube-apiserver] Checking if container is running on host [172.27.116.68]
DEBU[0059] [remove/kube-apiserver] Removing container on host [172.27.116.68]
INFO[0059] Removing container [kube-apiserver] on host [172.27.116.68], try #1
INFO[0068] [remove/kube-apiserver] Successfully removed container on host [172.27.116.68]
DEBU[0068] [remove/kube-controller-manager] Checking if container is running on host [172.27.116.68]
DEBU[0068] [remove/kube-controller-manager] Removing container on host [172.27.116.68]
INFO[0068] Removing container [kube-controller-manager] on host [172.27.116.68], try #1
INFO[0074] [remove/kube-controller-manager] Successfully removed container on host [172.27.116.68]
DEBU[0074] [remove/kube-scheduler] Checking if container is running on host [172.27.116.68]
DEBU[0074] [remove/kube-scheduler] Removing container on host [172.27.116.68]
INFO[0074] Removing container [kube-scheduler] on host [172.27.116.68], try #1
INFO[0088] [remove/kube-scheduler] Successfully removed container on host [172.27.116.68]
DEBU[0088] [remove/kubelet] Checking if container is running on host [172.27.116.68]
DEBU[0088] [remove/kubelet] Removing container on host [172.27.116.68]
INFO[0088] Removing container [kubelet] on host [172.27.116.68], try #1
INFO[0096] [remove/kubelet] Successfully removed container on host [172.27.116.68]
DEBU[0096] [remove/kube-proxy] Checking if container is running on host [172.27.116.68]
DEBU[0096] [remove/kube-proxy] Removing container on host [172.27.116.68]
INFO[0096] Removing container [kube-proxy] on host [172.27.116.68], try #1
INFO[0105] [remove/kube-proxy] Successfully removed container on host [172.27.116.68]
DEBU[0105] [remove/service-sidekick] Checking if container is running on host [172.27.116.68]
DEBU[0105] [remove/service-sidekick] Removing container on host [172.27.116.68]
INFO[0105] Removing container [service-sidekick] on host [172.27.116.68], try #1
INFO[0109] [remove/service-sidekick] Successfully removed container on host [172.27.116.68]
INFO[0109] [controlplane] Successfully tore down Controller Plane..
INFO[0109] [hosts] Cleaning up host [172.27.116.68]
DEBU[0109] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0109] [hosts] Running cleaner container on host [172.27.116.68]
DEBU[0109] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0109] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0110] Starting container [kube-cleaner] on host [172.27.116.68], try #1
INFO[0112] [kube-cleaner] Successfully started [kube-cleaner] container on host [172.27.116.68]
INFO[0112] Waiting for [kube-cleaner] container to exit on host [172.27.116.68]
DEBU[0113] Exit code for [kube-cleaner] container on host [172.27.116.68] is [0]
INFO[0113] [hosts] Removing cleaner container on host [172.27.116.68]
INFO[0113] Removing container [kube-cleaner] on host [172.27.116.68], try #1
INFO[0114] [hosts] Removing dead container logs on host [172.27.116.68]
DEBU[0114] [cleanup] Starting log link cleanup on host [172.27.116.68]
DEBU[0114] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.68]
DEBU[0114] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.68]
DEBU[0114] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0114] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0115] Starting container [rke-log-cleaner] on host [172.27.116.68], try #1
INFO[0117] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.68]
DEBU[0117] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.68]
DEBU[0118] [remove/rke-log-cleaner] Removing container on host [172.27.116.68]
INFO[0118] Removing container [rke-log-cleaner] on host [172.27.116.68], try #1
INFO[0118] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.68]
DEBU[0118] [cleanup] Successfully cleaned up log links on host [172.27.116.68]
INFO[0118] [hosts] Successfully cleaned up host [172.27.116.68]
INFO[0118] [reconcile] Rebuilding and updating local kube config
DEBU[0118] [reconcile] Rebuilding and updating local kube config, creating new kubeconfig
DEBU[0118] Deploying admin Kubeconfig locally at [./kube_config_cluster.yml]
INFO[0119] Successfully Deployed local admin kubeconfig at [./kube_config_cluster.yml]
DEBU[0119] [version] Using ./kube_config_cluster.yml to connect to Kubernetes cluster..
DEBU[0119] [version] Getting Kubernetes server version..
INFO[0119] [reconcile] host [172.27.116.65] is a control plane node with reachable Kubernetes API endpoint in the cluster
DEBU[0119] [restart/kube-apiserver] Checking if container is running on host [172.27.116.65]
DEBU[0119] [restart/kube-apiserver] Restarting container on host [172.27.116.65]
INFO[0119] Restarting container [kube-apiserver] on host [172.27.116.65], try #1
INFO[0130] [restart/kube-apiserver] Successfully restarted container on host [172.27.116.65]
DEBU[0130] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.65]
DEBU[0132] [restart/kube-controller-manager] Restarting container on host [172.27.116.65]
INFO[0132] Restarting container [kube-controller-manager] on host [172.27.116.65], try #1
INFO[0136] [restart/kube-controller-manager] Successfully restarted container on host [172.27.116.65]
DEBU[0136] [restart/kube-apiserver] Checking if container is running on host [172.27.116.66]
DEBU[0136] [restart/kube-apiserver] Restarting container on host [172.27.116.66]
INFO[0136] Restarting container [kube-apiserver] on host [172.27.116.66], try #1
INFO[0145] [restart/kube-apiserver] Successfully restarted container on host [172.27.116.66]
DEBU[0145] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.66]
DEBU[0145] [restart/kube-controller-manager] Restarting container on host [172.27.116.66]
INFO[0145] Restarting container [kube-controller-manager] on host [172.27.116.66], try #1
INFO[0149] [restart/kube-controller-manager] Successfully restarted container on host [172.27.116.66]
DEBU[0149] [restart/kube-apiserver] Checking if container is running on host [172.27.116.67]
DEBU[0149] [restart/kube-apiserver] Restarting container on host [172.27.116.67]
INFO[0149] Restarting container [kube-apiserver] on host [172.27.116.67], try #1
INFO[0158] [restart/kube-apiserver] Successfully restarted container on host [172.27.116.67]
DEBU[0158] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.67]
DEBU[0158] [restart/kube-controller-manager] Restarting container on host [172.27.116.67]
INFO[0158] Restarting container [kube-controller-manager] on host [172.27.116.67], try #1
INFO[0164] [restart/kube-controller-manager] Successfully restarted container on host [172.27.116.67]
DEBU[0164] [restart/etcd] Checking if container is running on host [ks-9047489]
DEBU[0164] [restart/etcd] Restarting container on host [ks-9047489]
INFO[0164] Restarting container [etcd] on host [ks-9047489], try #1
INFO[0171] [restart/etcd] Successfully restarted container on host [ks-9047489]
DEBU[0171] [restart/etcd] Checking if container is running on host [ks-9047366]
DEBU[0171] [restart/etcd] Restarting container on host [ks-9047366]
INFO[0171] Restarting container [etcd] on host [ks-9047366], try #1
INFO[0174] [restart/etcd] Successfully restarted container on host [ks-9047366]
DEBU[0174] [restart/etcd] Checking if container is running on host [ks-9047368]
DEBU[0174] [restart/etcd] Restarting container on host [ks-9047368]
INFO[0174] Restarting container [etcd] on host [ks-9047368], try #1
INFO[0179] [restart/etcd] Successfully restarted container on host [ks-9047368]
INFO[0179] [reconcile] Reconciled cluster state successfully
DEBU[0179] Provided value for maxUnavailable: {1 0 10%}
INFO[0179] max_unavailable_worker got rounded down to 0, resetting to 1
DEBU[0179] Parsed value of maxUnavailable: 1
DEBU[0179] Provided value for maxUnavailable: {0 1 }
DEBU[0179] Parsed value of maxUnavailable: 1
INFO[0179] Setting maxUnavailable for worker nodes to: 1
INFO[0179] Setting maxUnavailable for controlplane nodes to: 1
DEBU[0179] Encryption is disabled in both current and new spec; no action is required
INFO[0179] Pre-pulling kubernetes images
DEBU[0179] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66], try #1
DEBU[0179] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.67], try #1
DEBU[0179] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65], try #1
INFO[0179] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66]
INFO[0179] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65]
INFO[0179] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.67]
INFO[0179] Kubernetes images pulled successfully
DEBU[0179] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0179] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0179] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0179] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0179] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0179] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0179] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0179] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0179] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0179] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0179] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0179] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0179] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0179] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0179] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0179] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0179] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0179] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0179] [etcd] Building up etcd plane..
DEBU[0179] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0179] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0179] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0181] Starting container [etcd-fix-perm] on host [172.27.116.65], try #1
INFO[0184] Successfully started [etcd-fix-perm] container on host [172.27.116.65]
INFO[0184] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.65]
INFO[0184] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.65]
DEBU[0189] Exit code for [etcd-fix-perm] container on host [172.27.116.65] is [0]
DEBU[0189] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.65]
DEBU[0189] [remove/etcd-fix-perm] Removing container on host [172.27.116.65]
INFO[0189] Removing container [etcd-fix-perm] on host [172.27.116.65], try #1
INFO[0191] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.65]
DEBU[0191] [etcd] Container [etcd] is already running on host [172.27.116.65]
DEBU[0191] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.65]
DEBU[0191] slice is not equal, showing data in new value which is not in old value: map[--initial-cluster-state=new:{} --initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380:{}]
DEBU[0191] slice is not equal, showing data in old value which is not in new value: map[--initial-cluster-state=existing:{} --initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380,etcd-ks-9047988=https://172.27.116.58:2380:{}]
DEBU[0191] [etcd] Container [etcd] is eligible for upgrade on host [172.27.116.65]
DEBU[0191] [etcd] Checking for deployed [etcd]
INFO[0191] Checking if container [etcd] is running on host [172.27.116.65], try #1
DEBU[0191] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.65], try #1
INFO[0191] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.65]
DEBU[0191] [etcd] Stopping old container
INFO[0191] Checking if container [old-etcd] is running on host [172.27.116.65], try #1
INFO[0191] Stopping container [etcd] on host [172.27.116.65] with stopTimeoutDuration [5s], try #1
INFO[0197] Waiting for [etcd] container to exit on host [172.27.116.65]
DEBU[0197] Exit code for [etcd] container on host [172.27.116.65] is [0]
INFO[0197] Renaming container [etcd] to [old-etcd] on host [172.27.116.65], try #1
DEBU[0198] [etcd] Successfully stopped old container etcd on host [172.27.116.65]
INFO[0200] Starting container [etcd] on host [172.27.116.65], try #1
INFO[0201] [etcd] Successfully updated [etcd] container on host [172.27.116.65]
DEBU[0201] [etcd] Removing old container
INFO[0201] Removing container [old-etcd] on host [172.27.116.65], try #1
DEBU[0202] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0202] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0202] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0202] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.65]
DEBU[0202] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.55:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0202] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.65]
DEBU[0202] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.65]
INFO[0202] Removing container [etcd-rolling-snapshots] on host [172.27.116.65], try #1
INFO[0204] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.65]
DEBU[0204] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0204] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
INFO[0206] Starting container [etcd-rolling-snapshots] on host [172.27.116.65], try #1
INFO[0207] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.65]
DEBU[0212] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0212] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0212] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
INFO[0215] Starting container [rke-bundle-cert] on host [172.27.116.65], try #1
INFO[0218] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.65]
INFO[0218] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.65]
DEBU[0219] Exit code for [rke-bundle-cert] container on host [172.27.116.65] is [0]
INFO[0219] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.65]
INFO[0219] Removing container [rke-bundle-cert] on host [172.27.116.65], try #1
DEBU[0220] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0220] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0220] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0220] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0220] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0222] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0225] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0225] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0230] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0230] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0232] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0232] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0232] [etcd] Creating log link for Container [etcd] on host [172.27.116.65]
DEBU[0232] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0232] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0232] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0232] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0234] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0237] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0237] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0240] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0240] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0244] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0244] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.65]
DEBU[0244] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0244] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0244] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0245] Starting container [etcd-fix-perm] on host [172.27.116.66], try #1
INFO[0246] Successfully started [etcd-fix-perm] container on host [172.27.116.66]
INFO[0246] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.66]
INFO[0246] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.66]
DEBU[0248] Exit code for [etcd-fix-perm] container on host [172.27.116.66] is [0]
DEBU[0248] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.66]
DEBU[0248] [remove/etcd-fix-perm] Removing container on host [172.27.116.66]
INFO[0248] Removing container [etcd-fix-perm] on host [172.27.116.66], try #1
INFO[0248] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.66]
DEBU[0248] [etcd] Container [etcd] is already running on host [172.27.116.66]
DEBU[0248] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.66]
DEBU[0248] slice is not equal, showing data in new value which is not in old value: map[--initial-cluster-state=new:{} --initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380:{}]
DEBU[0248] slice is not equal, showing data in old value which is not in new value: map[--initial-cluster-state=existing:{} --initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380,etcd-ks-9047988=https://172.27.116.58:2380:{}]
DEBU[0248] [etcd] Container [etcd] is eligible for upgrade on host [172.27.116.66]
DEBU[0248] [etcd] Checking for deployed [etcd]
INFO[0248] Checking if container [etcd] is running on host [172.27.116.66], try #1
DEBU[0248] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.66], try #1
INFO[0248] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.66]
DEBU[0248] [etcd] Stopping old container
INFO[0248] Checking if container [old-etcd] is running on host [172.27.116.66], try #1
INFO[0248] Stopping container [etcd] on host [172.27.116.66] with stopTimeoutDuration [5s], try #1
INFO[0251] Waiting for [etcd] container to exit on host [172.27.116.66]
DEBU[0251] Exit code for [etcd] container on host [172.27.116.66] is [0]
INFO[0251] Renaming container [etcd] to [old-etcd] on host [172.27.116.66], try #1
DEBU[0251] [etcd] Successfully stopped old container etcd on host [172.27.116.66]
INFO[0251] Starting container [etcd] on host [172.27.116.66], try #1
INFO[0253] [etcd] Successfully updated [etcd] container on host [172.27.116.66]
DEBU[0253] [etcd] Removing old container
INFO[0253] Removing container [old-etcd] on host [172.27.116.66], try #1
DEBU[0253] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0253] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0253] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0253] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.66]
DEBU[0253] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.56:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0253] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.66]
DEBU[0253] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.66]
INFO[0253] Removing container [etcd-rolling-snapshots] on host [172.27.116.66], try #1
INFO[0255] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.66]
DEBU[0255] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0255] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
INFO[0256] Starting container [etcd-rolling-snapshots] on host [172.27.116.66], try #1
INFO[0258] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.66]
DEBU[0263] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0263] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0263] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
INFO[0263] Starting container [rke-bundle-cert] on host [172.27.116.66], try #1
INFO[0265] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.66]
INFO[0265] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.66]
DEBU[0266] Exit code for [rke-bundle-cert] container on host [172.27.116.66] is [0]
INFO[0266] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.66]
INFO[0266] Removing container [rke-bundle-cert] on host [172.27.116.66], try #1
DEBU[0266] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0266] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0266] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0266] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0266] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0267] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0269] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0269] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0270] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0270] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0271] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0271] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0271] [etcd] Creating log link for Container [etcd] on host [172.27.116.66]
DEBU[0271] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0271] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0271] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0271] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0272] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0273] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0273] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0274] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0274] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0275] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0275] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.66]
DEBU[0275] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0275] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0275] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0276] Starting container [etcd-fix-perm] on host [172.27.116.67], try #1
INFO[0278] Successfully started [etcd-fix-perm] container on host [172.27.116.67]
INFO[0278] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.67]
INFO[0278] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.67]
DEBU[0280] Exit code for [etcd-fix-perm] container on host [172.27.116.67] is [0]
DEBU[0280] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.67]
DEBU[0280] [remove/etcd-fix-perm] Removing container on host [172.27.116.67]
INFO[0280] Removing container [etcd-fix-perm] on host [172.27.116.67], try #1
INFO[0281] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.67]
DEBU[0281] [etcd] Container [etcd] is already running on host [172.27.116.67]
DEBU[0281] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.67]
DEBU[0281] slice is not equal, showing data in new value which is not in old value: map[--initial-cluster-state=new:{} --initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380:{}]
DEBU[0281] slice is not equal, showing data in old value which is not in new value: map[--initial-cluster-state=existing:{} --initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380,etcd-ks-9047988=https://172.27.116.58:2380:{}]
DEBU[0281] [etcd] Container [etcd] is eligible for upgrade on host [172.27.116.67]
DEBU[0281] [etcd] Checking for deployed [etcd]
INFO[0281] Checking if container [etcd] is running on host [172.27.116.67], try #1
DEBU[0281] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.67], try #1
INFO[0281] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.67]
DEBU[0281] [etcd] Stopping old container
INFO[0281] Checking if container [old-etcd] is running on host [172.27.116.67], try #1
INFO[0281] Stopping container [etcd] on host [172.27.116.67] with stopTimeoutDuration [5s], try #1
INFO[0283] Waiting for [etcd] container to exit on host [172.27.116.67]
DEBU[0283] Exit code for [etcd] container on host [172.27.116.67] is [0]
INFO[0283] Renaming container [etcd] to [old-etcd] on host [172.27.116.67], try #1
DEBU[0283] [etcd] Successfully stopped old container etcd on host [172.27.116.67]
INFO[0284] Starting container [etcd] on host [172.27.116.67], try #1
INFO[0285] [etcd] Successfully updated [etcd] container on host [172.27.116.67]
DEBU[0285] [etcd] Removing old container
INFO[0285] Removing container [old-etcd] on host [172.27.116.67], try #1
DEBU[0285] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0285] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0285] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0285] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.67]
DEBU[0285] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.57:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.67]
DEBU[0285] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.67]
DEBU[0285] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.67]
INFO[0285] Removing container [etcd-rolling-snapshots] on host [172.27.116.67], try #1
INFO[0288] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.67]
DEBU[0288] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67], try #1
INFO[0288] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67]
INFO[0289] Starting container [etcd-rolling-snapshots] on host [172.27.116.67], try #1
INFO[0290] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.67]
DEBU[0295] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0295] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67], try #1
INFO[0295] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67]
INFO[0296] Starting container [rke-bundle-cert] on host [172.27.116.67], try #1
INFO[0298] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.67]
INFO[0298] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.67]
DEBU[0299] Exit code for [rke-bundle-cert] container on host [172.27.116.67] is [0]
INFO[0299] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.67]
INFO[0299] Removing container [rke-bundle-cert] on host [172.27.116.67], try #1
DEBU[0300] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.67]
DEBU[0300] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0300] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.67]
DEBU[0300] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0300] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0302] Starting container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0304] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.67]
DEBU[0304] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0306] [remove/rke-log-linker] Removing container on host [172.27.116.67]
INFO[0306] Removing container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0307] [remove/rke-log-linker] Successfully removed container on host [172.27.116.67]
DEBU[0307] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.67]
DEBU[0307] [etcd] Creating log link for Container [etcd] on host [172.27.116.67]
DEBU[0307] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0307] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.67]
DEBU[0307] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0307] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0308] Starting container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0310] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.67]
DEBU[0310] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0311] [remove/rke-log-linker] Removing container on host [172.27.116.67]
INFO[0311] Removing container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0311] [remove/rke-log-linker] Successfully removed container on host [172.27.116.67]
DEBU[0311] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.67]
INFO[0311] [etcd] Successfully started etcd plane.. Checking etcd cluster health
DEBU[0311] [etcd] check etcd cluster health on host [172.27.116.65]
INFO[0312] [etcd] etcd host [172.27.116.65] reported healthy=true
DEBU[0312] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0312] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0312] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0312] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0312] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0312] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0312] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0312] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0312] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0312] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0312] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0312] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0312] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0312] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0312] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0312] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0312] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0312] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0312] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0312] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0312] [controlplane] Now checking status of node ks-9047489, try #1
DEBU[0312] Checking node list for node [ks-9047489], try #1
DEBU[0312] [controlplane] Found node by name ks-9047489
INFO[0312] [controlplane] Now checking status of node ks-9047366, try #1
DEBU[0312] Checking node list for node [ks-9047366], try #1
DEBU[0312] [controlplane] Found node by name ks-9047366
INFO[0312] [controlplane] Now checking status of node ks-9047368, try #1
DEBU[0312] Checking node list for node [ks-9047368], try #1
DEBU[0312] [controlplane] Found node by name ks-9047368
INFO[0312] [controlplane] Processing controlplane hosts for upgrade 1 at a time
INFO[0312] Processing controlplane host ks-9047489
INFO[0312] [controlplane] Now checking status of node ks-9047489, try #1
DEBU[0312] Checking node list for node [ks-9047489], try #1
DEBU[0312] [controlplane] Found node by name ks-9047489
INFO[0312] [controlplane] Getting list of nodes for upgrade
DEBU[0312] [controlplane] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.65]
DEBU[0312] [controlplane] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.65]
DEBU[0312] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.65]
DEBU[0312] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.57:2379:{}]
DEBU[0312] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.57:2379,https://172.27.116.58:2379:{}]
DEBU[0312] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.65]
DEBU[0312] [controlplane] Host ks-9047489 is upgradable because kube-apiserver has changed
DEBU[0312] [worker] Checking if container [nginx-proxy] is eligible for upgrade on host [172.27.116.65]
DEBU[0312] [worker] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.65]
DEBU[0312] [worker] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.65]
DEBU[0312] [worker] Checking if container [kubelet] is eligible for upgrade on host [172.27.116.65]
DEBU[0312] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0312] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0312] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0312] [worker] Container [kubelet] is not eligible for upgrade on host [172.27.116.65]
DEBU[0312] [worker] Checking if container [kube-proxy] is eligible for upgrade on host [172.27.116.65]
DEBU[0312] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0312] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0312] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0312] [worker] Container [kube-proxy] is not eligible for upgrade on host [172.27.116.65]
DEBU[0312] [worker] Host ks-9047489 is not upgradable
DEBU[0312] [controlplane] Cordoning node ks-9047489
DEBU[0312] Checking node list for node [ks-9047489], try #1
DEBU[0312] Checking node list for node [ks-9047489], try #1
DEBU[0312] Node ks-9047489 is already cordoned: true
INFO[0312] Upgrading controlplane components for control host ks-9047489
DEBU[0312] [remove/nginx-proxy] Checking if container is running on host [172.27.116.65]
DEBU[0312] [remove/nginx-proxy] Container doesn't exist on host [172.27.116.65]
INFO[0312] Checking if container [service-sidekick] is running on host [172.27.116.65], try #1
DEBU[0312] [sidekick] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.65]
DEBU[0312] [sidekick] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.65]
INFO[0312] [sidekick] Sidekick container already created on host [172.27.116.65]
DEBU[0312] [controlplane] Container [kube-apiserver] is already running on host [172.27.116.65]
DEBU[0312] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.65]
DEBU[0312] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.57:2379:{}]
DEBU[0312] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.57:2379,https://172.27.116.58:2379:{}]
DEBU[0312] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.65]
DEBU[0312] [controlplane] Checking for deployed [kube-apiserver]
INFO[0312] Checking if container [kube-apiserver] is running on host [172.27.116.65], try #1
DEBU[0312] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65], try #1
INFO[0312] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65]
DEBU[0312] [controlplane] Stopping old container
INFO[0312] Checking if container [old-kube-apiserver] is running on host [172.27.116.65], try #1
INFO[0312] Stopping container [kube-apiserver] on host [172.27.116.65] with stopTimeoutDuration [5s], try #1
INFO[0319] Waiting for [kube-apiserver] container to exit on host [172.27.116.65]
DEBU[0319] Exit code for [kube-apiserver] container on host [172.27.116.65] is [137]
INFO[0319] Renaming container [kube-apiserver] to [old-kube-apiserver] on host [172.27.116.65], try #1
DEBU[0320] [controlplane] Successfully stopped old container kube-apiserver on host [172.27.116.65]
INFO[0321] Starting container [kube-apiserver] on host [172.27.116.65], try #1
INFO[0325] [controlplane] Successfully updated [kube-apiserver] container on host [172.27.116.65]
DEBU[0325] [controlplane] Removing old container
INFO[0325] Removing container [old-kube-apiserver] on host [172.27.116.65], try #1
INFO[0332] [healthcheck] Start Healthcheck on service [kube-apiserver] on host [172.27.116.65]
INFO[0332] [healthcheck] service [kube-apiserver] on host [172.27.116.65] is healthy
DEBU[0332] [controlplane] Creating log link for Container [kube-apiserver] on host [172.27.116.65]
DEBU[0332] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0332] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0332] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0332] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0334] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0336] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0336] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0338] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0338] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0338] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0338] [controlplane] Successfully created log link for Container [kube-apiserver] on host [172.27.116.65]
DEBU[0338] [controlplane] Container [kube-controller-manager] is already running on host [172.27.116.65]
DEBU[0338] [controlplane] Checking if container [kube-controller-manager] is eligible for upgrade on host [172.27.116.65]
DEBU[0338] [controlplane] Container [kube-controller-manager] is not eligible for upgrade on host [172.27.116.65]
INFO[0338] [healthcheck] Start Healthcheck on service [kube-controller-manager] on host [172.27.116.65]
INFO[0338] [healthcheck] service [kube-controller-manager] on host [172.27.116.65] is healthy
DEBU[0338] [controlplane] Creating log link for Container [kube-controller-manager] on host [172.27.116.65]
DEBU[0338] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0338] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0338] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0338] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0339] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0340] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0340] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0342] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0342] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0342] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0342] [controlplane] Successfully created log link for Container [kube-controller-manager] on host [172.27.116.65]
DEBU[0342] [controlplane] Container [kube-scheduler] is already running on host [172.27.116.65]
DEBU[0342] [controlplane] Checking if container [kube-scheduler] is eligible for upgrade on host [172.27.116.65]
DEBU[0342] [controlplane] Container [kube-scheduler] is not eligible for upgrade on host [172.27.116.65]
INFO[0342] [healthcheck] Start Healthcheck on service [kube-scheduler] on host [172.27.116.65]
INFO[0342] [healthcheck] service [kube-scheduler] on host [172.27.116.65] is healthy
DEBU[0342] [controlplane] Creating log link for Container [kube-scheduler] on host [172.27.116.65]
DEBU[0342] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0342] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0342] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0342] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0343] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0345] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0345] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0346] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0346] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0347] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0347] [controlplane] Successfully created log link for Container [kube-scheduler] on host [172.27.116.65]
INFO[0347] [controlplane] Now checking status of node ks-9047489, try #1
DEBU[0347] Checking node list for node [ks-9047489], try #1
DEBU[0347] [controlplane] Found node by name ks-9047489
DEBU[0347] Checking node list for node [ks-9047489], try #1
DEBU[0347] Checking node list for node [ks-9047489], try #1
DEBU[0347] Node ks-9047489 is already cordoned: false
INFO[0347] Processing controlplane host ks-9047366
INFO[0347] [controlplane] Now checking status of node ks-9047366, try #1
DEBU[0347] Checking node list for node [ks-9047366], try #1
DEBU[0347] [controlplane] Found node by name ks-9047366
INFO[0347] [controlplane] Getting list of nodes for upgrade
DEBU[0347] [controlplane] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.66]
DEBU[0347] [controlplane] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.66]
DEBU[0347] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.66]
DEBU[0347] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.56:2379,https://172.27.116.55:2379,https://172.27.116.57:2379:{}]
DEBU[0347] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.56:2379,https://172.27.116.55:2379,https://172.27.116.57:2379,https://172.27.116.58:2379:{}]
DEBU[0347] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.66]
DEBU[0347] [controlplane] Host ks-9047366 is upgradable because kube-apiserver has changed
DEBU[0347] [worker] Checking if container [nginx-proxy] is eligible for upgrade on host [172.27.116.66]
DEBU[0347] [worker] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.66]
DEBU[0347] [worker] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.66]
DEBU[0347] [worker] Checking if container [kubelet] is eligible for upgrade on host [172.27.116.66]
DEBU[0347] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0347] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0347] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0347] [worker] Container [kubelet] is not eligible for upgrade on host [172.27.116.66]
DEBU[0347] [worker] Checking if container [kube-proxy] is eligible for upgrade on host [172.27.116.66]
DEBU[0347] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0347] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0347] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0347] [worker] Container [kube-proxy] is not eligible for upgrade on host [172.27.116.66]
DEBU[0347] [worker] Host ks-9047366 is not upgradable
DEBU[0347] [controlplane] Cordoning node ks-9047366
DEBU[0347] Checking node list for node [ks-9047366], try #1
DEBU[0347] Checking node list for node [ks-9047366], try #1
DEBU[0347] Node ks-9047366 is already cordoned: true
INFO[0347] Upgrading controlplane components for control host ks-9047366
DEBU[0347] [remove/nginx-proxy] Checking if container is running on host [172.27.116.66]
DEBU[0347] [remove/nginx-proxy] Container doesn't exist on host [172.27.116.66]
INFO[0347] Checking if container [service-sidekick] is running on host [172.27.116.66], try #1
DEBU[0347] [sidekick] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.66]
DEBU[0347] [sidekick] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.66]
INFO[0347] [sidekick] Sidekick container already created on host [172.27.116.66]
DEBU[0347] [controlplane] Container [kube-apiserver] is already running on host [172.27.116.66]
DEBU[0347] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.66]
DEBU[0347] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.56:2379,https://172.27.116.55:2379,https://172.27.116.57:2379:{}]
DEBU[0347] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.56:2379,https://172.27.116.55:2379,https://172.27.116.57:2379,https://172.27.116.58:2379:{}]
DEBU[0347] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.66]
DEBU[0347] [controlplane] Checking for deployed [kube-apiserver]
INFO[0347] Checking if container [kube-apiserver] is running on host [172.27.116.66], try #1
DEBU[0347] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66], try #1
INFO[0347] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66]
DEBU[0347] [controlplane] Stopping old container
INFO[0347] Checking if container [old-kube-apiserver] is running on host [172.27.116.66], try #1
INFO[0347] Stopping container [kube-apiserver] on host [172.27.116.66] with stopTimeoutDuration [5s], try #1
INFO[0354] Waiting for [kube-apiserver] container to exit on host [172.27.116.66]
DEBU[0354] Exit code for [kube-apiserver] container on host [172.27.116.66] is [137]
INFO[0354] Renaming container [kube-apiserver] to [old-kube-apiserver] on host [172.27.116.66], try #1
DEBU[0354] [controlplane] Successfully stopped old container kube-apiserver on host [172.27.116.66]
INFO[0355] Starting container [kube-apiserver] on host [172.27.116.66], try #1
INFO[0356] [controlplane] Successfully updated [kube-apiserver] container on host [172.27.116.66]
DEBU[0356] [controlplane] Removing old container
INFO[0356] Removing container [old-kube-apiserver] on host [172.27.116.66], try #1
INFO[0359] [healthcheck] Start Healthcheck on service [kube-apiserver] on host [172.27.116.66]
DEBU[0360] [healthcheck] Service [kube-apiserver] is not healthy on host [172.27.116.66]. Response code: [500], response body: [+]ping ok
[+]log ok
[+]etcd ok
[+]poststarthook/start-kube-apiserver-admission-initializer ok
[+]poststarthook/generic-apiserver-start-informers ok
[+]poststarthook/priority-and-fairness-config-consumer ok
[+]poststarthook/priority-and-fairness-filter ok
[+]poststarthook/start-apiextensions-informers ok
[+]poststarthook/start-apiextensions-controllers ok
[+]poststarthook/crd-informer-synced ok
[-]poststarthook/bootstrap-controller failed: reason withheld
[-]poststarthook/rbac/bootstrap-roles failed: reason withheld
[-]poststarthook/scheduling/bootstrap-system-priority-classes failed: reason withheld
[-]poststarthook/priority-and-fairness-config-producer failed: reason withheld
[+]poststarthook/start-cluster-authentication-info-controller ok
[+]poststarthook/aggregator-reload-proxy-client-cert ok
[+]poststarthook/start-kube-aggregator-informers ok
[+]poststarthook/apiservice-registration-controller ok
[+]poststarthook/apiservice-status-available-controller ok
[+]poststarthook/kube-apiserver-autoregistration ok
[+]autoregister-completion ok
[+]poststarthook/apiservice-openapi-controller ok
healthz check failed
, try #1
INFO[0365] [healthcheck] service [kube-apiserver] on host [172.27.116.66] is healthy
DEBU[0365] [controlplane] Creating log link for Container [kube-apiserver] on host [172.27.116.66]
DEBU[0365] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0365] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0365] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0365] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0366] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0368] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0368] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0369] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0369] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0369] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0369] [controlplane] Successfully created log link for Container [kube-apiserver] on host [172.27.116.66]
DEBU[0369] [controlplane] Container [kube-controller-manager] is already running on host [172.27.116.66]
DEBU[0369] [controlplane] Checking if container [kube-controller-manager] is eligible for upgrade on host [172.27.116.66]
DEBU[0369] [controlplane] Container [kube-controller-manager] is not eligible for upgrade on host [172.27.116.66]
INFO[0369] [healthcheck] Start Healthcheck on service [kube-controller-manager] on host [172.27.116.66]
INFO[0369] [healthcheck] service [kube-controller-manager] on host [172.27.116.66] is healthy
DEBU[0369] [controlplane] Creating log link for Container [kube-controller-manager] on host [172.27.116.66]
DEBU[0369] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0369] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0369] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0369] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0371] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0372] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0372] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0374] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0374] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0374] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0374] [controlplane] Successfully created log link for Container [kube-controller-manager] on host [172.27.116.66]
DEBU[0374] [controlplane] Container [kube-scheduler] is already running on host [172.27.116.66]
DEBU[0374] [controlplane] Checking if container [kube-scheduler] is eligible for upgrade on host [172.27.116.66]
DEBU[0374] [controlplane] Container [kube-scheduler] is not eligible for upgrade on host [172.27.116.66]
INFO[0374] [healthcheck] Start Healthcheck on service [kube-scheduler] on host [172.27.116.66]
INFO[0374] [healthcheck] service [kube-scheduler] on host [172.27.116.66] is healthy
DEBU[0374] [controlplane] Creating log link for Container [kube-scheduler] on host [172.27.116.66]
DEBU[0374] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0374] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0374] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0374] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0376] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0377] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0377] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0378] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0378] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0379] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0379] [controlplane] Successfully created log link for Container [kube-scheduler] on host [172.27.116.66]
INFO[0379] [controlplane] Now checking status of node ks-9047366, try #1
DEBU[0379] Checking node list for node [ks-9047366], try #1
DEBU[0379] [controlplane] Found node by name ks-9047366
DEBU[0379] Checking node list for node [ks-9047366], try #1
DEBU[0379] Checking node list for node [ks-9047366], try #1
DEBU[0379] Node ks-9047366 is already cordoned: false
INFO[0379] Processing controlplane host ks-9047368
INFO[0379] [controlplane] Now checking status of node ks-9047368, try #1
DEBU[0379] Checking node list for node [ks-9047368], try #1
DEBU[0379] [controlplane] Found node by name ks-9047368
INFO[0379] [controlplane] Getting list of nodes for upgrade
DEBU[0379] [controlplane] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.67]
DEBU[0379] [controlplane] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.67]
DEBU[0379] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.67]
DEBU[0379] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.57:2379,https://172.27.116.55:2379,https://172.27.116.56:2379:{}]
DEBU[0379] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.57:2379,https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.58:2379:{}]
DEBU[0379] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.67]
DEBU[0379] [controlplane] Host ks-9047368 is upgradable because kube-apiserver has changed
DEBU[0379] [worker] Checking if container [nginx-proxy] is eligible for upgrade on host [172.27.116.67]
DEBU[0379] [worker] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.67]
DEBU[0379] [worker] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.67]
DEBU[0379] [worker] Checking if container [kubelet] is eligible for upgrade on host [172.27.116.67]
DEBU[0379] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0379] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0379] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0379] [worker] Container [kubelet] is not eligible for upgrade on host [172.27.116.67]
DEBU[0379] [worker] Checking if container [kube-proxy] is eligible for upgrade on host [172.27.116.67]
DEBU[0379] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0379] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0379] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0379] [worker] Container [kube-proxy] is not eligible for upgrade on host [172.27.116.67]
DEBU[0379] [worker] Host ks-9047368 is not upgradable
DEBU[0379] [controlplane] Cordoning node ks-9047368
DEBU[0379] Checking node list for node [ks-9047368], try #1
DEBU[0379] Checking node list for node [ks-9047368], try #1
DEBU[0379] Node ks-9047368 is already cordoned: true
INFO[0379] Upgrading controlplane components for control host ks-9047368
DEBU[0379] [remove/nginx-proxy] Checking if container is running on host [172.27.116.67]
DEBU[0379] [remove/nginx-proxy] Container doesn't exist on host [172.27.116.67]
INFO[0379] Checking if container [service-sidekick] is running on host [172.27.116.67], try #1
DEBU[0379] [sidekick] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.67]
DEBU[0379] [sidekick] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.67]
INFO[0379] [sidekick] Sidekick container already created on host [172.27.116.67]
DEBU[0379] [controlplane] Container [kube-apiserver] is already running on host [172.27.116.67]
DEBU[0379] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.67]
DEBU[0379] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.57:2379,https://172.27.116.55:2379,https://172.27.116.56:2379:{}]
DEBU[0379] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.57:2379,https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.58:2379:{}]
DEBU[0379] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.67]
DEBU[0379] [controlplane] Checking for deployed [kube-apiserver]
INFO[0379] Checking if container [kube-apiserver] is running on host [172.27.116.67], try #1
DEBU[0379] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.67], try #1
INFO[0379] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.67]
DEBU[0379] [controlplane] Stopping old container
INFO[0379] Checking if container [old-kube-apiserver] is running on host [172.27.116.67], try #1
INFO[0379] Stopping container [kube-apiserver] on host [172.27.116.67] with stopTimeoutDuration [5s], try #1
INFO[0386] Waiting for [kube-apiserver] container to exit on host [172.27.116.67]
DEBU[0386] Exit code for [kube-apiserver] container on host [172.27.116.67] is [137]
INFO[0386] Renaming container [kube-apiserver] to [old-kube-apiserver] on host [172.27.116.67], try #1
DEBU[0387] [controlplane] Successfully stopped old container kube-apiserver on host [172.27.116.67]
INFO[0389] Starting container [kube-apiserver] on host [172.27.116.67], try #1
INFO[0390] [controlplane] Successfully updated [kube-apiserver] container on host [172.27.116.67]
DEBU[0390] [controlplane] Removing old container
INFO[0390] Removing container [old-kube-apiserver] on host [172.27.116.67], try #1
INFO[0395] [healthcheck] Start Healthcheck on service [kube-apiserver] on host [172.27.116.67]
DEBU[0396] [healthcheck] Service [kube-apiserver] is not healthy on host [172.27.116.67]. Response code: [500], response body: [+]ping ok
[+]log ok
[+]etcd ok
[+]poststarthook/start-kube-apiserver-admission-initializer ok
[+]poststarthook/generic-apiserver-start-informers ok
[+]poststarthook/priority-and-fairness-config-consumer ok
[+]poststarthook/priority-and-fairness-filter ok
[+]poststarthook/start-apiextensions-informers ok
[+]poststarthook/start-apiextensions-controllers ok
[+]poststarthook/crd-informer-synced ok
[+]poststarthook/bootstrap-controller ok
[-]poststarthook/rbac/bootstrap-roles failed: reason withheld
[-]poststarthook/scheduling/bootstrap-system-priority-classes failed: reason withheld
[-]poststarthook/priority-and-fairness-config-producer failed: reason withheld
[+]poststarthook/start-cluster-authentication-info-controller ok
[+]poststarthook/aggregator-reload-proxy-client-cert ok
[+]poststarthook/start-kube-aggregator-informers ok
[+]poststarthook/apiservice-registration-controller ok
[+]poststarthook/apiservice-status-available-controller ok
[+]poststarthook/kube-apiserver-autoregistration ok
[+]autoregister-completion ok
[+]poststarthook/apiservice-openapi-controller ok
healthz check failed
, try #1
INFO[0401] [healthcheck] service [kube-apiserver] on host [172.27.116.67] is healthy
DEBU[0401] [controlplane] Creating log link for Container [kube-apiserver] on host [172.27.116.67]
DEBU[0401] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0401] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.67]
DEBU[0401] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0401] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0401] Starting container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0403] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.67]
DEBU[0403] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0404] [remove/rke-log-linker] Removing container on host [172.27.116.67]
INFO[0404] Removing container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0405] [remove/rke-log-linker] Successfully removed container on host [172.27.116.67]
DEBU[0405] [controlplane] Successfully created log link for Container [kube-apiserver] on host [172.27.116.67]
DEBU[0405] [controlplane] Container [kube-controller-manager] is already running on host [172.27.116.67]
DEBU[0405] [controlplane] Checking if container [kube-controller-manager] is eligible for upgrade on host [172.27.116.67]
DEBU[0405] [controlplane] Container [kube-controller-manager] is not eligible for upgrade on host [172.27.116.67]
INFO[0405] [healthcheck] Start Healthcheck on service [kube-controller-manager] on host [172.27.116.67]
INFO[0405] [healthcheck] service [kube-controller-manager] on host [172.27.116.67] is healthy
DEBU[0405] [controlplane] Creating log link for Container [kube-controller-manager] on host [172.27.116.67]
DEBU[0405] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0405] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.67]
DEBU[0405] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0405] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0406] Starting container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0407] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.67]
DEBU[0407] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0409] [remove/rke-log-linker] Removing container on host [172.27.116.67]
INFO[0409] Removing container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0409] [remove/rke-log-linker] Successfully removed container on host [172.27.116.67]
DEBU[0409] [controlplane] Successfully created log link for Container [kube-controller-manager] on host [172.27.116.67]
DEBU[0409] [controlplane] Container [kube-scheduler] is already running on host [172.27.116.67]
DEBU[0409] [controlplane] Checking if container [kube-scheduler] is eligible for upgrade on host [172.27.116.67]
DEBU[0409] [controlplane] Container [kube-scheduler] is not eligible for upgrade on host [172.27.116.67]
INFO[0409] [healthcheck] Start Healthcheck on service [kube-scheduler] on host [172.27.116.67]
INFO[0410] [healthcheck] service [kube-scheduler] on host [172.27.116.67] is healthy
DEBU[0410] [controlplane] Creating log link for Container [kube-scheduler] on host [172.27.116.67]
DEBU[0410] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0410] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.67]
DEBU[0410] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0410] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0411] Starting container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0412] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.67]
DEBU[0412] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0413] [remove/rke-log-linker] Removing container on host [172.27.116.67]
INFO[0413] Removing container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0414] [remove/rke-log-linker] Successfully removed container on host [172.27.116.67]
DEBU[0414] [controlplane] Successfully created log link for Container [kube-scheduler] on host [172.27.116.67]
INFO[0414] [controlplane] Now checking status of node ks-9047368, try #1
DEBU[0414] Checking node list for node [ks-9047368], try #1
DEBU[0414] [controlplane] Found node by name ks-9047368
DEBU[0414] Checking node list for node [ks-9047368], try #1
DEBU[0414] Checking node list for node [ks-9047368], try #1
DEBU[0414] Node ks-9047368 is already cordoned: false
INFO[0414] [controlplane] Successfully upgraded Controller Plane..
DEBU[0414] Checking if cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0414] Cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0414] Enabling kube-api audit log for cluster version [v1.22.10-rancher1-1]
DEBU[0414] Host: 172.27.116.65 has role: etcd
DEBU[0414] Host: 172.27.116.65 has role: controlplane
DEBU[0414] Host: 172.27.116.65 has role: worker
DEBU[0414] Host: 172.27.116.66 has role: etcd
DEBU[0414] Host: 172.27.116.66 has role: controlplane
DEBU[0414] Host: 172.27.116.66 has role: worker
DEBU[0414] Host: 172.27.116.67 has role: etcd
DEBU[0414] Host: 172.27.116.67 has role: controlplane
DEBU[0414] Host: 172.27.116.67 has role: worker
INFO[0414] [authz] Creating rke-job-deployer ServiceAccount
INFO[0415] [authz] rke-job-deployer ServiceAccount created successfully
INFO[0415] [authz] Creating system:node ClusterRoleBinding
INFO[0415] [authz] system:node ClusterRoleBinding created successfully
INFO[0415] [authz] Creating kube-apiserver proxy ClusterRole and ClusterRoleBinding
INFO[0415] [authz] kube-apiserver proxy ClusterRole and ClusterRoleBinding created successfully
INFO[0415] Successfully Deployed state file at [./cluster.rkestate]
INFO[0415] [state] Saving full cluster state to Kubernetes
INFO[0415] [state] Successfully Saved full cluster state to Kubernetes ConfigMap: full-cluster-state
DEBU[0415] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0415] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0415] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0415] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0415] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0415] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0415] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0415] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0415] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0415] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0415] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0415] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0415] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0415] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0415] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0415] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0415] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0415] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0415] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0415] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0415] [worker] Upgrading Worker Plane..
INFO[0415] [worker] Successfully upgraded Worker Plane..
DEBU[0415] [cleanup] Starting log link cleanup on host [172.27.116.66]
DEBU[0415] [cleanup] Starting log link cleanup on host [172.27.116.65]
DEBU[0415] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.66]
DEBU[0415] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.65]
DEBU[0415] [cleanup] Starting log link cleanup on host [172.27.116.67]
DEBU[0415] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.67]
DEBU[0415] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.66]
DEBU[0415] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.67]
DEBU[0415] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
DEBU[0415] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0415] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0415] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
DEBU[0415] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.65]
DEBU[0415] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0415] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0416] Starting container [rke-log-cleaner] on host [172.27.116.65], try #1
INFO[0416] Starting container [rke-log-cleaner] on host [172.27.116.67], try #1
INFO[0416] Starting container [rke-log-cleaner] on host [172.27.116.66], try #1
INFO[0418] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.66]
DEBU[0418] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.66]
INFO[0418] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.65]
DEBU[0418] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.65]
INFO[0418] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.67]
DEBU[0418] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.67]
DEBU[0419] [remove/rke-log-cleaner] Removing container on host [172.27.116.65]
INFO[0419] Removing container [rke-log-cleaner] on host [172.27.116.65], try #1
DEBU[0419] [remove/rke-log-cleaner] Removing container on host [172.27.116.66]
INFO[0419] Removing container [rke-log-cleaner] on host [172.27.116.66], try #1
DEBU[0419] [remove/rke-log-cleaner] Removing container on host [172.27.116.67]
INFO[0419] Removing container [rke-log-cleaner] on host [172.27.116.67], try #1
INFO[0419] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.66]
DEBU[0419] [cleanup] Successfully cleaned up log links on host [172.27.116.66]
INFO[0419] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.65]
DEBU[0419] [cleanup] Successfully cleaned up log links on host [172.27.116.65]
INFO[0419] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.67]
DEBU[0419] [cleanup] Successfully cleaned up log links on host [172.27.116.67]
INFO[0419] [sync] Syncing nodes Labels and Taints
DEBU[0419] worker [9] starting sync for node [ks-9047366]
DEBU[0419] Checking node list for node [ks-9047366], try #1
DEBU[0419] worker [0] starting sync for node [ks-9047489]
DEBU[0419] Checking node list for node [ks-9047489], try #1
DEBU[0419] worker [4] starting sync for node [ks-9047368]
DEBU[0419] Checking node list for node [ks-9047368], try #1
DEBU[0419] skipping syncing labels for node [ks-9047489]
DEBU[0419] skipping syncing labels for node [ks-9047368]
DEBU[0420] skipping syncing labels for node [ks-9047366]
INFO[0420] [sync] Successfully synced nodes Labels and Taints
DEBU[0420] Checking if cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0420] Cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0420] Enabling kube-api audit log for cluster version [v1.22.10-rancher1-1]
DEBU[0420] Host: 172.27.116.65 has role: etcd
DEBU[0420] Host: 172.27.116.65 has role: controlplane
DEBU[0420] Host: 172.27.116.65 has role: worker
DEBU[0420] Host: 172.27.116.66 has role: etcd
DEBU[0420] Host: 172.27.116.66 has role: controlplane
DEBU[0420] Host: 172.27.116.66 has role: worker
DEBU[0420] Host: 172.27.116.67 has role: etcd
DEBU[0420] Host: 172.27.116.67 has role: controlplane
DEBU[0420] Host: 172.27.116.67 has role: worker
INFO[0420] [network] Setting up network plugin: flannel
INFO[0420] [addons] Saving ConfigMap for addon rke-network-plugin to Kubernetes
INFO[0420] [addons] Successfully saved ConfigMap for addon rke-network-plugin to Kubernetes
INFO[0420] [addons] Executing deploy job rke-network-plugin
DEBU[0420] Checking node list for node [ks-9047489], try #1
DEBU[0420] Checking addon job OS label for cluster version [v1.22.10-rancher1-1]
DEBU[0420] Cluster version [v1.22.10-rancher1-1] needs to use new OS label
DEBU[0420] [k8s] Job rke-network-plugin-deploy-job already exists..
INFO[0420] [addons] Setting up coredns
INFO[0420] [addons] Saving ConfigMap for addon rke-coredns-addon to Kubernetes
INFO[0420] [addons] Successfully saved ConfigMap for addon rke-coredns-addon to Kubernetes
INFO[0420] [addons] Executing deploy job rke-coredns-addon
DEBU[0420] Checking node list for node [ks-9047489], try #1
DEBU[0420] Checking addon job OS label for cluster version [v1.22.10-rancher1-1]
DEBU[0420] Cluster version [v1.22.10-rancher1-1] needs to use new OS label
DEBU[0420] [k8s] Job rke-coredns-addon-deploy-job already exists..
INFO[0420] [addons] CoreDNS deployed successfully
INFO[0420] [dns] DNS provider coredns deployed successfully
INFO[0420] [addons] Setting up Metrics Server
INFO[0420] [addons] Saving ConfigMap for addon rke-metrics-addon to Kubernetes
INFO[0420] [addons] Successfully saved ConfigMap for addon rke-metrics-addon to Kubernetes
INFO[0420] [addons] Executing deploy job rke-metrics-addon
DEBU[0420] Checking node list for node [ks-9047489], try #1
DEBU[0420] Checking addon job OS label for cluster version [v1.22.10-rancher1-1]
DEBU[0420] Cluster version [v1.22.10-rancher1-1] needs to use new OS label
DEBU[0420] [k8s] Job rke-metrics-addon-deploy-job already exists..
INFO[0420] [addons] Metrics Server deployed successfully
INFO[0420] [ingress] Setting up nginx ingress controller
INFO[0420] [ingress] removing admission batch jobs if they exist
INFO[0420] [addons] Saving ConfigMap for addon rke-ingress-controller to Kubernetes
INFO[0420] [addons] Successfully saved ConfigMap for addon rke-ingress-controller to Kubernetes
INFO[0420] [addons] Executing deploy job rke-ingress-controller
DEBU[0420] Checking node list for node [ks-9047489], try #1
DEBU[0420] Checking addon job OS label for cluster version [v1.22.10-rancher1-1]
DEBU[0420] Cluster version [v1.22.10-rancher1-1] needs to use new OS label
DEBU[0420] [k8s] Job rke-ingress-controller-deploy-job already exists..
INFO[0420] [ingress] removing default backend service and deployment if they exist
INFO[0420] [ingress] ingress controller nginx deployed successfully
INFO[0420] [addons] Setting up user addons
INFO[0420] [addons] no user addons defined
INFO[0420] Finished building Kubernetes cluster successfully
root@ks-9047489:~#
```  
We can use docker command to inspect the etcd, kube-apiserver, kube-scheduler, kube-controller-manager status.  
```sh  
# the containers uptime almost the same as 16 minutes.
root@ks-9047366:~# docker ps -a|grep -E 'kube-|etcd'
2a8174bfb7a7   rancher/hyperkube:v1.22.10-rancher1                "/opt/rke-tools/entr…"   15 minutes ago   Up 15 minutes                         kube-apiserver
06dc9fe4b030   rancher/rke-tools:v0.1.80                          "/docker-entrypoint.…"   16 minutes ago   Up 16 minutes                         etcd-rolling-snapshots
5aebfe3ac1e0   rancher/mirrored-coreos-etcd:v3.5.0                "/usr/local/bin/etcd…"   16 minutes ago   Up 16 minutes                         etcd
5f19b4e05409   e6ea68648f0c                                       "/opt/bin/flanneld -…"   23 hours ago     Up 23 hours                           k8s_kube-flannel_kube-flannel-hdqpn_kube-system_25d73a12-3d85-4a86-9325-aec7fc6f36e5_3
af53c740af00   204d7aaf689a                                       "/install-cni.sh"        23 hours ago     Up 23 hours                           k8s_install-cni_kube-flannel-hdqpn_kube-system_25d73a12-3d85-4a86-9325-aec7fc6f36e5_3
f8af8d9544bb   rancher/mirrored-pause:3.6                         "/pause"                 23 hours ago     Up 23 hours                           k8s_POD_kube-flannel-hdqpn_kube-system_25d73a12-3d85-4a86-9325-aec7fc6f36e5_3
df5f24e8f37b   e6ea68648f0c                                       "/opt/bin/flanneld -…"   2 days ago       Exited (255) 23 hours ago             k8s_kube-flannel_kube-flannel-hdqpn_kube-system_25d73a12-3d85-4a86-9325-aec7fc6f36e5_2
0893db2b9716   204d7aaf689a                                       "/install-cni.sh"        2 days ago       Exited (255) 23 hours ago             k8s_install-cni_kube-flannel-hdqpn_kube-system_25d73a12-3d85-4a86-9325-aec7fc6f36e5_2
64bb9d16ef4c   rancher/mirrored-pause:3.6                         "/pause"                 2 days ago       Exited (255) 23 hours ago             k8s_POD_kube-flannel-hdqpn_kube-system_25d73a12-3d85-4a86-9325-aec7fc6f36e5_2
f0d9c86e9d02   rancher/hyperkube:v1.22.10-rancher1                "/opt/rke-tools/entr…"   7 days ago       Up 23 hours                           kube-proxy
cd2f70b07c76   rancher/hyperkube:v1.22.10-rancher1                "/opt/rke-tools/entr…"   7 days ago       Up 15 minutes                         kube-scheduler
750db7f84f04   rancher/hyperkube:v1.22.10-rancher1                "/opt/rke-tools/entr…"   7 days ago       Up 15 minutes                         kube-controller-manager

```  
```sh  
root@ks-9047366:~# docker inspect etcd
```  
```json  
            "Cmd": [
                "/usr/local/bin/etcd",
                "--data-dir=/var/lib/rancher/etcd/",
                "--initial-cluster-token=etcd-cluster-1",
                "--listen-client-urls=https://172.27.116.56:2379",
                "--advertise-client-urls=https://172.27.116.56:2379",
                "--name=etcd-ks-9047366",
                "--initial-cluster-state=new",
                "--trusted-ca-file=/etc/kubernetes/ssl/kube-ca.pem",
                "--cipher-suites=TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384",
                "--election-timeout=5000",
                "--peer-client-cert-auth=true",
                "--heartbeat-interval=500",
                "--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380",
                "--cert-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem",
                "--key-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem",
                "--peer-cert-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem",
                "--client-cert-auth=true",
                "--initial-advertise-peer-urls=https://172.27.116.56:2380",
                "--listen-peer-urls=https://172.27.116.56:2380",
                "--peer-trusted-ca-file=/etc/kubernetes/ssl/kube-ca.pem",
                "--peer-key-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem"
            ],

```  