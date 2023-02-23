There is one cluster consist of 3 nodes.  
+ ks-9047489 (172.27.116.65/172.27.116.55) (etcd, controlplane, worker)  
+ ks-9047366 (172.27.116.66/172.27.116.56) (etcd, controlplane, worker)  
> `not truely 2 nodes, we remove 1 node from 4 nodes cluster in before.`  

Use rke tool to update(add) ks-9047368 node role back of cluster.  
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
INFO[0000] [dialer] Setup tunnel for host [172.27.116.66]
INFO[0000] [dialer] Setup tunnel for host [172.27.116.67]
INFO[0000] [dialer] Setup tunnel for host [172.27.116.65]
DEBU[0000] Connecting to Docker API for host [172.27.116.67]
DEBU[0000] Connecting to Docker API for host [172.27.116.66]
DEBU[0000] Connecting to Docker API for host [172.27.116.65]
DEBU[0000] Docker Info found for host [172.27.116.66]: types.Info{ID:"7T67:DXEC:PYY6:VISK:5RG4:M2UV:N6NE:MAI4:QNBJ:PXN6:JNZ3:E6XT", Containers:45, ContainersRunning:41, ContainersPaused:0, ContainersStopped:4, Images:43, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:168, OomKillDisable:true, NGoroutines:148, SystemTime:"2023-02-22T17:17:27.341556721+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc00011a0e0), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047366", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
DEBU[0000] Docker Info found for host [172.27.116.67]: types.Info{ID:"VN5L:TH7K:7SRQ:LLCZ:F7QU:TJUR:7AZ7:ETFA:NIKN:KE4N:OEJE:KWUZ", Containers:48, ContainersRunning:42, ContainersPaused:0, ContainersStopped:6, Images:32, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:175, OomKillDisable:true, NGoroutines:149, SystemTime:"2023-02-22T17:17:27.194313013+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc00070c460), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047368", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
DEBU[0000] Docker Info found for host [172.27.116.65]: types.Info{ID:"PXEX:4WFR:EIA2:YQWO:7QYJ:AV77:D5FS:5CXU:O7VZ:7V3L:V24Y:IHH2", Containers:142, ContainersRunning:100, ContainersPaused:0, ContainersStopped:42, Images:47, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:481, OomKillDisable:true, NGoroutines:382, SystemTime:"2023-02-22T17:17:26.805302826+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc00070c690), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047489", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
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
INFO[0000] [network] No hosts added existing cluster, skipping port check
DEBU[0000] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0000] [certificates] kube-apiserver certificate changed, force deploying certs
INFO[0000] [certificates] Deploying kubernetes certificates to Cluster nodes
INFO[0000] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
INFO[0000] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0000] Checking if container [cert-deployer] is running on host [172.27.116.67], try #1
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67], try #1
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67]
DEBU[0000] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
DEBU[0000] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
DEBU[0000] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0001] Starting container [cert-deployer] on host [172.27.116.66], try #1
INFO[0001] Starting container [cert-deployer] on host [172.27.116.67], try #1
INFO[0001] Starting container [cert-deployer] on host [172.27.116.65], try #1
DEBU[0002] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0002] Checking if container [cert-deployer] is running on host [172.27.116.67], try #1
DEBU[0002] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0002] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
DEBU[0003] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0003] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
INFO[0007] Checking if container [cert-deployer] is running on host [172.27.116.67], try #1
INFO[0007] Removing container [cert-deployer] on host [172.27.116.67], try #1
INFO[0007] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0007] Removing container [cert-deployer] on host [172.27.116.65], try #1
INFO[0008] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
INFO[0008] Removing container [cert-deployer] on host [172.27.116.66], try #1
INFO[0009] [reconcile] Rebuilding and updating local kube config
DEBU[0009] [reconcile] Rebuilding and updating local kube config, creating new kubeconfig
DEBU[0009] Deploying admin Kubeconfig locally at [./kube_config_cluster.yml]
INFO[0009] Successfully Deployed local admin kubeconfig at [./kube_config_cluster.yml]
DEBU[0009] [version] Using ./kube_config_cluster.yml to connect to Kubernetes cluster..
DEBU[0009] [version] Getting Kubernetes server version..
INFO[0009] [reconcile] host [172.27.116.65] is a control plane node with reachable Kubernetes API endpoint in the cluster
INFO[0009] [certificates] Successfully deployed kubernetes certificates to Cluster nodes
INFO[0009] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.65]
DEBU[0009] [remove/file-deployer] Checking if container is running on host [172.27.116.65]
DEBU[0009] [remove/file-deployer] Container doesn't exist on host [172.27.116.65]
DEBU[0009] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0009] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0009] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0010] Starting container [file-deployer] on host [172.27.116.65], try #1
INFO[0013] Successfully started [file-deployer] container on host [172.27.116.65]
INFO[0013] Waiting for [file-deployer] container to exit on host [172.27.116.65]
INFO[0013] Waiting for [file-deployer] container to exit on host [172.27.116.65]
DEBU[0015] Exit code for [file-deployer] container on host [172.27.116.65] is [0]
DEBU[0015] [remove/file-deployer] Checking if container is running on host [172.27.116.65]
DEBU[0015] [remove/file-deployer] Removing container on host [172.27.116.65]
INFO[0015] Removing container [file-deployer] on host [172.27.116.65], try #1
INFO[0015] [remove/file-deployer] Successfully removed container on host [172.27.116.65]
DEBU[0015] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.65]
INFO[0015] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.66]
DEBU[0015] [remove/file-deployer] Checking if container is running on host [172.27.116.66]
DEBU[0015] [remove/file-deployer] Container doesn't exist on host [172.27.116.66]
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0015] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0017] Starting container [file-deployer] on host [172.27.116.66], try #1
INFO[0019] Successfully started [file-deployer] container on host [172.27.116.66]
INFO[0019] Waiting for [file-deployer] container to exit on host [172.27.116.66]
INFO[0019] Waiting for [file-deployer] container to exit on host [172.27.116.66]
DEBU[0020] Exit code for [file-deployer] container on host [172.27.116.66] is [0]
DEBU[0020] [remove/file-deployer] Checking if container is running on host [172.27.116.66]
DEBU[0020] [remove/file-deployer] Removing container on host [172.27.116.66]
INFO[0020] Removing container [file-deployer] on host [172.27.116.66], try #1
INFO[0021] [remove/file-deployer] Successfully removed container on host [172.27.116.66]
DEBU[0021] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.66]
INFO[0021] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.67]
DEBU[0021] [remove/file-deployer] Checking if container is running on host [172.27.116.67]
DEBU[0021] [remove/file-deployer] Container doesn't exist on host [172.27.116.67]
DEBU[0021] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0021] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0021] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0022] Starting container [file-deployer] on host [172.27.116.67], try #1
INFO[0023] Successfully started [file-deployer] container on host [172.27.116.67]
INFO[0023] Waiting for [file-deployer] container to exit on host [172.27.116.67]
INFO[0023] Waiting for [file-deployer] container to exit on host [172.27.116.67]
DEBU[0024] Exit code for [file-deployer] container on host [172.27.116.67] is [0]
DEBU[0024] [remove/file-deployer] Checking if container is running on host [172.27.116.67]
DEBU[0024] [remove/file-deployer] Removing container on host [172.27.116.67]
INFO[0024] Removing container [file-deployer] on host [172.27.116.67], try #1
INFO[0024] [remove/file-deployer] Successfully removed container on host [172.27.116.67]
DEBU[0024] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.67]
INFO[0024] [/etc/kubernetes/audit-policy.yaml] Successfully deployed audit policy file to Cluster control nodes
INFO[0024] [reconcile] Reconciling cluster state
INFO[0024] [reconcile] Check etcd hosts to be deleted
DEBU[0024] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0024] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0024] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0024] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0024] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0024] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0024] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0024] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0024] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0024] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0024] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0024] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0024] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0024] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0024] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0024] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0024] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0024] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0024] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0024] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0024] [reconcile] Check etcd hosts to be added
DEBU[0024] [reconcile] Check worker hosts to be deleted
DEBU[0024] [reconcile] Check Control plane hosts to be deleted
INFO[0024] [reconcile] Rebuilding and updating local kube config
DEBU[0024] [reconcile] Rebuilding and updating local kube config, creating new kubeconfig
DEBU[0024] Deploying admin Kubeconfig locally at [./kube_config_cluster.yml]
INFO[0024] Successfully Deployed local admin kubeconfig at [./kube_config_cluster.yml]
DEBU[0024] [version] Using ./kube_config_cluster.yml to connect to Kubernetes cluster..
DEBU[0024] [version] Getting Kubernetes server version..
INFO[0024] [reconcile] host [172.27.116.65] is a control plane node with reachable Kubernetes API endpoint in the cluster
DEBU[0024] [restart/kube-apiserver] Checking if container is running on host [172.27.116.67]
DEBU[0024] [restart/kube-apiserver] Container doesn't exist on host [172.27.116.67]
DEBU[0024] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.67]
DEBU[0024] [restart/kube-controller-manager] Container doesn't exist on host [172.27.116.67]
DEBU[0024] [restart/kube-apiserver] Checking if container is running on host [172.27.116.65]
DEBU[0024] [restart/kube-apiserver] Restarting container on host [172.27.116.65]
INFO[0024] Restarting container [kube-apiserver] on host [172.27.116.65], try #1
INFO[0032] [restart/kube-apiserver] Successfully restarted container on host [172.27.116.65]
DEBU[0032] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.65]
DEBU[0032] [restart/kube-controller-manager] Restarting container on host [172.27.116.65]
INFO[0032] Restarting container [kube-controller-manager] on host [172.27.116.65], try #1
INFO[0035] [restart/kube-controller-manager] Successfully restarted container on host [172.27.116.65]
DEBU[0035] [restart/kube-apiserver] Checking if container is running on host [172.27.116.66]
DEBU[0036] [restart/kube-apiserver] Restarting container on host [172.27.116.66]
INFO[0036] Restarting container [kube-apiserver] on host [172.27.116.66], try #1
INFO[0045] [restart/kube-apiserver] Successfully restarted container on host [172.27.116.66]
DEBU[0045] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.66]
DEBU[0046] [restart/kube-controller-manager] Restarting container on host [172.27.116.66]
INFO[0046] Restarting container [kube-controller-manager] on host [172.27.116.66], try #1
INFO[0048] [restart/kube-controller-manager] Successfully restarted container on host [172.27.116.66]
DEBU[0048] [restart/etcd] Checking if container is running on host [ks-9047489]
DEBU[0048] [restart/etcd] Restarting container on host [ks-9047489]
INFO[0048] Restarting container [etcd] on host [ks-9047489], try #1
INFO[0050] [restart/etcd] Successfully restarted container on host [ks-9047489]
DEBU[0050] [restart/etcd] Checking if container is running on host [ks-9047366]
DEBU[0050] [restart/etcd] Restarting container on host [ks-9047366]
INFO[0050] Restarting container [etcd] on host [ks-9047366], try #1
INFO[0052] [restart/etcd] Successfully restarted container on host [ks-9047366]
DEBU[0052] [restart/etcd] Checking if container is running on host [ks-9047368]
DEBU[0052] [restart/etcd] Container doesn't exist on host [ks-9047368]
INFO[0052] [reconcile] Reconciled cluster state successfully
DEBU[0052] Provided value for maxUnavailable: {1 0 10%}
INFO[0052] max_unavailable_worker got rounded down to 0, resetting to 1
DEBU[0052] Parsed value of maxUnavailable: 1
DEBU[0052] Provided value for maxUnavailable: {0 1 }
DEBU[0052] Parsed value of maxUnavailable: 1
INFO[0052] Setting maxUnavailable for worker nodes to: 1
INFO[0052] Setting maxUnavailable for controlplane nodes to: 1
DEBU[0052] Encryption is disabled in both current and new spec; no action is required
INFO[0052] Pre-pulling kubernetes images
DEBU[0052] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65], try #1
DEBU[0052] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66], try #1
DEBU[0052] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.67], try #1
INFO[0052] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65]
INFO[0052] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.67]
INFO[0052] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66]
INFO[0052] Kubernetes images pulled successfully
DEBU[0052] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0052] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0052] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0052] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0052] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0052] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0052] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0052] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0052] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0052] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0052] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0052] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0052] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0052] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0052] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0052] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0052] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0052] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0052] [etcd] Building up etcd plane..
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0052] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0053] Starting container [etcd-fix-perm] on host [172.27.116.65], try #1
INFO[0055] Successfully started [etcd-fix-perm] container on host [172.27.116.65]
INFO[0055] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.65]
INFO[0055] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.65]
DEBU[0057] Exit code for [etcd-fix-perm] container on host [172.27.116.65] is [0]
DEBU[0057] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.65]
DEBU[0057] [remove/etcd-fix-perm] Removing container on host [172.27.116.65]
INFO[0057] Removing container [etcd-fix-perm] on host [172.27.116.65], try #1
INFO[0058] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.65]
DEBU[0058] [etcd] Container [etcd] is already running on host [172.27.116.65]
DEBU[0058] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.65]
DEBU[0058] slice is not equal, showing data in new value which is not in old value: map[--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380:{}]
DEBU[0058] slice is not equal, showing data in old value which is not in new value: map[--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380:{}]
DEBU[0058] [etcd] Container [etcd] is eligible for upgrade on host [172.27.116.65]
DEBU[0058] [etcd] Checking for deployed [etcd]
INFO[0058] Checking if container [etcd] is running on host [172.27.116.65], try #1
DEBU[0058] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.65], try #1
INFO[0058] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.65]
DEBU[0058] [etcd] Stopping old container
INFO[0058] Checking if container [old-etcd] is running on host [172.27.116.65], try #1
INFO[0058] Stopping container [etcd] on host [172.27.116.65] with stopTimeoutDuration [5s], try #1
INFO[0059] Waiting for [etcd] container to exit on host [172.27.116.65]
DEBU[0059] Exit code for [etcd] container on host [172.27.116.65] is [2]
INFO[0059] Renaming container [etcd] to [old-etcd] on host [172.27.116.65], try #1
DEBU[0059] [etcd] Successfully stopped old container etcd on host [172.27.116.65]
INFO[0059] Starting container [etcd] on host [172.27.116.65], try #1
INFO[0060] [etcd] Successfully updated [etcd] container on host [172.27.116.65]
DEBU[0060] [etcd] Removing old container
INFO[0060] Removing container [old-etcd] on host [172.27.116.65], try #1
DEBU[0061] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0061] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0061] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0061] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.65]
DEBU[0061] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.55:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0061] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.65]
DEBU[0061] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.65]
INFO[0061] Removing container [etcd-rolling-snapshots] on host [172.27.116.65], try #1
INFO[0062] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.65]
DEBU[0062] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0062] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
INFO[0063] Starting container [etcd-rolling-snapshots] on host [172.27.116.65], try #1
INFO[0065] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.65]
DEBU[0070] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0070] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0070] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
INFO[0071] Starting container [rke-bundle-cert] on host [172.27.116.65], try #1
INFO[0073] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.65]
INFO[0073] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.65]
DEBU[0074] Exit code for [rke-bundle-cert] container on host [172.27.116.65] is [0]
INFO[0074] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.65]
INFO[0074] Removing container [rke-bundle-cert] on host [172.27.116.65], try #1
DEBU[0075] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0075] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0075] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0075] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0075] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0076] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0079] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0079] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0082] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0082] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0083] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0083] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0083] [etcd] Creating log link for Container [etcd] on host [172.27.116.65]
DEBU[0083] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0083] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0083] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0083] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0084] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0085] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0085] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0086] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0086] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0087] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0087] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.65]
DEBU[0087] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0087] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0087] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0087] Starting container [etcd-fix-perm] on host [172.27.116.66], try #1
INFO[0090] Successfully started [etcd-fix-perm] container on host [172.27.116.66]
INFO[0090] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.66]
INFO[0090] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.66]
DEBU[0091] Exit code for [etcd-fix-perm] container on host [172.27.116.66] is [0]
DEBU[0091] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.66]
DEBU[0091] [remove/etcd-fix-perm] Removing container on host [172.27.116.66]
INFO[0091] Removing container [etcd-fix-perm] on host [172.27.116.66], try #1
INFO[0092] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.66]
DEBU[0092] [etcd] Container [etcd] is in a restarting loop [172.27.116.66]
INFO[0092] Restarting container [etcd] on host [172.27.116.66], try #1
DEBU[0094] [etcd] Container [etcd] is already running on host [172.27.116.66]
DEBU[0094] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.66]
DEBU[0094] slice is not equal, showing data in new value which is not in old value: map[--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380:{}]
DEBU[0094] slice is not equal, showing data in old value which is not in new value: map[--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380:{}]
DEBU[0094] [etcd] Container [etcd] is eligible for upgrade on host [172.27.116.66]
DEBU[0094] [etcd] Checking for deployed [etcd]
INFO[0094] Checking if container [etcd] is running on host [172.27.116.66], try #1
DEBU[0094] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.66], try #1
INFO[0094] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.66]
DEBU[0094] [etcd] Stopping old container
INFO[0094] Checking if container [old-etcd] is running on host [172.27.116.66], try #1
INFO[0094] Stopping container [etcd] on host [172.27.116.66] with stopTimeoutDuration [5s], try #1
INFO[0095] Waiting for [etcd] container to exit on host [172.27.116.66]
DEBU[0095] Exit code for [etcd] container on host [172.27.116.66] is [2]
INFO[0095] Renaming container [etcd] to [old-etcd] on host [172.27.116.66], try #1
DEBU[0095] [etcd] Successfully stopped old container etcd on host [172.27.116.66]
INFO[0096] Starting container [etcd] on host [172.27.116.66], try #1
INFO[0097] [etcd] Successfully updated [etcd] container on host [172.27.116.66]
DEBU[0097] [etcd] Removing old container
INFO[0097] Removing container [old-etcd] on host [172.27.116.66], try #1
DEBU[0098] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0098] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0098] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0098] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.66]
DEBU[0098] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.56:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0098] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.66]
DEBU[0098] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.66]
INFO[0098] Removing container [etcd-rolling-snapshots] on host [172.27.116.66], try #1
INFO[0099] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.66]
DEBU[0099] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0099] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
INFO[0100] Starting container [etcd-rolling-snapshots] on host [172.27.116.66], try #1
INFO[0102] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.66]
DEBU[0107] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0107] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0107] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
INFO[0108] Starting container [rke-bundle-cert] on host [172.27.116.66], try #1
INFO[0109] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.66]
INFO[0109] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.66]
DEBU[0111] Exit code for [rke-bundle-cert] container on host [172.27.116.66] is [0]
INFO[0111] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.66]
INFO[0111] Removing container [rke-bundle-cert] on host [172.27.116.66], try #1
DEBU[0112] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0112] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0112] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0112] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0112] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0112] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0115] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0115] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0119] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0119] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0120] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0120] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0120] [etcd] Creating log link for Container [etcd] on host [172.27.116.66]
DEBU[0120] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0120] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0120] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0120] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0120] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0122] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0122] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0123] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0123] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0124] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0124] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.66]
DEBU[0124] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0124] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0124] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0124] Starting container [etcd-fix-perm] on host [172.27.116.67], try #1
INFO[0126] Successfully started [etcd-fix-perm] container on host [172.27.116.67]
INFO[0126] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.67]
INFO[0126] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.67]
DEBU[0127] Exit code for [etcd-fix-perm] container on host [172.27.116.67] is [0]
DEBU[0127] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.67]
DEBU[0127] [remove/etcd-fix-perm] Removing container on host [172.27.116.67]
INFO[0127] Removing container [etcd-fix-perm] on host [172.27.116.67], try #1
INFO[0127] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.67]
DEBU[0127] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.67], try #1
INFO[0127] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.67]
INFO[0128] Starting container [etcd] on host [172.27.116.67], try #1
INFO[0129] [etcd] Successfully started [etcd] container on host [172.27.116.67]
DEBU[0129] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0129] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0129] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0129] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.67]
DEBU[0129] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.57:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.67]
DEBU[0129] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.67]
DEBU[0129] [remove/etcd-rolling-snapshots] Container doesn't exist on host [172.27.116.67]
DEBU[0129] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67], try #1
INFO[0129] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67]
INFO[0130] Starting container [etcd-rolling-snapshots] on host [172.27.116.67], try #1
INFO[0131] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.67]
DEBU[0136] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0136] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67], try #1
INFO[0136] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67]
INFO[0137] Starting container [rke-bundle-cert] on host [172.27.116.67], try #1
INFO[0138] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.67]
INFO[0138] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.67]
DEBU[0139] Exit code for [rke-bundle-cert] container on host [172.27.116.67] is [0]
INFO[0139] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.67]
INFO[0139] Removing container [rke-bundle-cert] on host [172.27.116.67], try #1
DEBU[0140] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.67]
DEBU[0140] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0140] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.67]
DEBU[0140] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0140] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0141] Starting container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0142] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.67]
DEBU[0142] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0144] [remove/rke-log-linker] Removing container on host [172.27.116.67]
INFO[0144] Removing container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0145] [remove/rke-log-linker] Successfully removed container on host [172.27.116.67]
DEBU[0145] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.67]
DEBU[0145] [etcd] Creating log link for Container [etcd] on host [172.27.116.67]
DEBU[0145] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0145] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.67]
DEBU[0145] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0145] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0146] Starting container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0147] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.67]
DEBU[0147] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0148] [remove/rke-log-linker] Removing container on host [172.27.116.67]
INFO[0148] Removing container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0149] [remove/rke-log-linker] Successfully removed container on host [172.27.116.67]
DEBU[0149] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.67]
INFO[0149] [etcd] Successfully started etcd plane.. Checking etcd cluster health
DEBU[0149] [etcd] check etcd cluster health on host [172.27.116.65]
DEBU[0149] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0154] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0159] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0164] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0169] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0174] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0179] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0184] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0189] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0195] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": EOF
DEBU[0200] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0206] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0211] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0216] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0221] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0226] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0231] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0236] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
WARN[0241] [etcd] host [172.27.116.65] failed to check etcd health: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0241] [etcd] check etcd cluster health on host [172.27.116.66]
DEBU[0241] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0246] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0251] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0257] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0262] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0267] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0272] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0277] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0282] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0287] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0292] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0297] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0303] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0308] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0313] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0318] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0323] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0328] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
WARN[0333] [etcd] host [172.27.116.66] failed to check etcd health: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0333] [etcd] check etcd cluster health on host [172.27.116.67]
DEBU[0343] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": net/http: TLS handshake timeout
DEBU[0358] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": EOF
DEBU[0373] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": net/http: TLS handshake timeout
DEBU[0383] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": EOF
DEBU[0398] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": net/http: TLS handshake timeout
DEBU[0413] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": net/http: TLS handshake timeout
DEBU[0420] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": EOF
DEBU[0435] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": net/http: TLS handshake timeout
DEBU[0445] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": EOF
DEBU[0460] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": net/http: TLS handshake timeout
DEBU[0475] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": net/http: TLS handshake timeout
DEBU[0482] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": EOF
DEBU[0498] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": net/http: TLS handshake timeout
DEBU[0507] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": EOF
DEBU[0522] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": net/http: TLS handshake timeout
DEBU[0537] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": net/http: TLS handshake timeout
DEBU[0546] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": EOF
DEBU[0561] [etcd] failed to check health for etcd host [172.27.116.67]: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": net/http: TLS handshake timeout
WARN[0566] [etcd] host [172.27.116.67] failed to check etcd health: failed to get /health for host [172.27.116.67]: Get "https://172.27.116.57:2379/health": net/http: TLS handshake timeout
FATA[0566] [etcd] Failed to bring up Etcd Plane: etcd cluster is unhealthy: hosts [172.27.116.65,172.27.116.66,172.27.116.67] failed to report healthy. Check etcd container logs on each host for more information
root@ks-9047489:~#
```  