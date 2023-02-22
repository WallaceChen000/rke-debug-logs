There is one cluster consist of 3 nodes.  
+ ks-9047489 (172.27.116.65/172.27.116.55) (etcd, controlplane, worker)  
+ ks-9047366 (172.27.116.66/172.27.116.56) (etcd, controlplane, worker)  
+ ks-9047368 (172.27.116.67/172.27.116.57) (etcd, controlplane, worker)  
> `not truely 3 nodes, we remove 1 node from 4 nodes cluster in before.`  

Use rke tool to update(remove) ks-9047368 node role out of cluster.  
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
DEBU[0000] [state] previous state found, this is not a legacy cluster
INFO[0000] [certificates] GenerateServingCertificate is disabled, checking if there are unused kubelet certificates
INFO[0000] [certificates] Generating Kubernetes API server certificates
INFO[0000] [certificates] Generating admin certificates and kubeconfig
INFO[0000] [certificates] Generating kube-etcd-172-27-116-55 certificate and key
INFO[0000] [certificates] Generating kube-etcd-172-27-116-56 certificate and key
INFO[0000] [certificates] Deleting unused certificate: kube-etcd-172-27-116-57
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
INFO[0000] Building Kubernetes cluster
INFO[0000] [dialer] Setup tunnel for host [172.27.116.66]
INFO[0000] [dialer] Setup tunnel for host [172.27.116.65]
DEBU[0000] Connecting to Docker API for host [172.27.116.66]
DEBU[0000] Connecting to Docker API for host [172.27.116.65]
DEBU[0000] Docker Info found for host [172.27.116.66]: types.Info{ID:"7T67:DXEC:PYY6:VISK:5RG4:M2UV:N6NE:MAI4:QNBJ:PXN6:JNZ3:E6XT", Containers:47, ContainersRunning:45, ContainersPaused:0, ContainersStopped:2, Images:43, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:178, OomKillDisable:true, NGoroutines:154, SystemTime:"2023-02-22T16:09:39.747844548+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc000464690), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047366", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
DEBU[0000] Docker Info found for host [172.27.116.65]: types.Info{ID:"PXEX:4WFR:EIA2:YQWO:7QYJ:AV77:D5FS:5CXU:O7VZ:7V3L:V24Y:IHH2", Containers:142, ContainersRunning:103, ContainersPaused:0, ContainersStopped:39, Images:47, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:490, OomKillDisable:true, NGoroutines:385, SystemTime:"2023-02-22T16:09:40.189222108+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc0004647e0), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047489", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
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
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
DEBU[0000] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
DEBU[0000] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0001] Starting container [cert-deployer] on host [172.27.116.65], try #1
INFO[0001] Starting container [cert-deployer] on host [172.27.116.66], try #1
DEBU[0003] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0003] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
DEBU[0003] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0003] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
INFO[0008] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0008] Removing container [cert-deployer] on host [172.27.116.65], try #1
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
INFO[0011] Starting container [file-deployer] on host [172.27.116.65], try #1
INFO[0014] Successfully started [file-deployer] container on host [172.27.116.65]
INFO[0014] Waiting for [file-deployer] container to exit on host [172.27.116.65]
INFO[0014] Waiting for [file-deployer] container to exit on host [172.27.116.65]
DEBU[0016] Exit code for [file-deployer] container on host [172.27.116.65] is [0]
DEBU[0016] [remove/file-deployer] Checking if container is running on host [172.27.116.65]
DEBU[0016] [remove/file-deployer] Removing container on host [172.27.116.65]
INFO[0016] Removing container [file-deployer] on host [172.27.116.65], try #1
INFO[0017] [remove/file-deployer] Successfully removed container on host [172.27.116.65]
DEBU[0017] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.65]
INFO[0017] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.66]
DEBU[0017] [remove/file-deployer] Checking if container is running on host [172.27.116.66]
DEBU[0017] [remove/file-deployer] Container doesn't exist on host [172.27.116.66]
DEBU[0017] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0017] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0017] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0018] Starting container [file-deployer] on host [172.27.116.66], try #1
INFO[0021] Successfully started [file-deployer] container on host [172.27.116.66]
INFO[0021] Waiting for [file-deployer] container to exit on host [172.27.116.66]
INFO[0021] Waiting for [file-deployer] container to exit on host [172.27.116.66]
DEBU[0023] Exit code for [file-deployer] container on host [172.27.116.66] is [0]
DEBU[0023] [remove/file-deployer] Checking if container is running on host [172.27.116.66]
DEBU[0023] [remove/file-deployer] Removing container on host [172.27.116.66]
INFO[0023] Removing container [file-deployer] on host [172.27.116.66], try #1
INFO[0023] [remove/file-deployer] Successfully removed container on host [172.27.116.66]
DEBU[0023] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.66]
INFO[0023] [/etc/kubernetes/audit-policy.yaml] Successfully deployed audit policy file to Cluster control nodes
INFO[0023] [reconcile] Reconciling cluster state
INFO[0023] [reconcile] Check etcd hosts to be deleted
DEBU[0023] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0023] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0023] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0023] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0023] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0023] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0023] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0023] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0023] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0023] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0023] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0023] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0023] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0023] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0023] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0023] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0023] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0023] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0023] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0023] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0023] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0023] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0023] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0023] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0023] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0023] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0023] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0023] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0023] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0023] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0023] [remove/etcd] Removing member [etcd-ks-9047368] from etcd cluster
INFO[0023] [remove/etcd] Checking etcd cluster health on [etcd-ks-9047489] after removing [etcd-ks-9047368]
DEBU[0023] [remove/etcd] healthCheckURL for checking etcd cluster health on [etcd-ks-9047489] after removing [ks-9047368]: [https://172.27.116.55:2379/health]
DEBU[0023] [etcd] check etcd cluster health on host [172.27.116.65]
INFO[0023] [etcd] etcd host [172.27.116.65] reported healthy=true
INFO[0023] [remove/etcd] etcd cluster health is healthy on [etcd-ks-9047489] after removing [etcd-ks-9047368]
DEBU[0023] Total time between etcd member deleted and etcd cluster healthy is: [112.602922ms]
INFO[0023] [remove/etcd] Successfully removed member [etcd-ks-9047368] from etcd cluster
INFO[0023] [hosts] host [172.27.116.67] has another role, skipping delete from kubernetes cluster
INFO[0023] [dialer] Setup tunnel for host [172.27.116.67]
DEBU[0023] Connecting to Docker API for host [172.27.116.67]
DEBU[0023] Docker Info found for host [172.27.116.67]: types.Info{ID:"VN5L:TH7K:7SRQ:LLCZ:F7QU:TJUR:7AZ7:ETFA:NIKN:KE4N:OEJE:KWUZ", Containers:56, ContainersRunning:50, ContainersPaused:0, ContainersStopped:6, Images:32, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:215, OomKillDisable:true, NGoroutines:183, SystemTime:"2023-02-22T16:10:04.216259985+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc00047e070), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047368", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
INFO[0023] [etcd] Tearing down etcd plane..
DEBU[0023] [remove/etcd] Checking if container is running on host [172.27.116.67]
DEBU[0024] [remove/etcd] Removing container on host [172.27.116.67]
INFO[0024] Removing container [etcd] on host [172.27.116.67], try #1
INFO[0026] [remove/etcd] Successfully removed container on host [172.27.116.67]
DEBU[0026] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.67]
DEBU[0026] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.67]
INFO[0026] Removing container [etcd-rolling-snapshots] on host [172.27.116.67], try #1
INFO[0027] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.67]
INFO[0027] [etcd] Successfully tore down etcd plane..
INFO[0027] [hosts] Host [172.27.116.67] is already a worker or control host, skipping cleanup certs.
INFO[0027] [hosts] Cleaning up host [172.27.116.67]
DEBU[0027] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0027] [hosts] Running cleaner container on host [172.27.116.67]
DEBU[0027] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0027] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0028] Starting container [kube-cleaner] on host [172.27.116.67], try #1
INFO[0030] [kube-cleaner] Successfully started [kube-cleaner] container on host [172.27.116.67]
INFO[0030] Waiting for [kube-cleaner] container to exit on host [172.27.116.67]
DEBU[0031] Exit code for [kube-cleaner] container on host [172.27.116.67] is [0]
INFO[0031] [hosts] Removing cleaner container on host [172.27.116.67]
INFO[0031] Removing container [kube-cleaner] on host [172.27.116.67], try #1
INFO[0031] [hosts] Removing dead container logs on host [172.27.116.67]
DEBU[0031] [cleanup] Starting log link cleanup on host [172.27.116.67]
DEBU[0031] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.67]
DEBU[0031] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.67]
DEBU[0031] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0031] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0032] Starting container [rke-log-cleaner] on host [172.27.116.67], try #1
INFO[0034] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.67]
DEBU[0034] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.67]
DEBU[0035] [remove/rke-log-cleaner] Removing container on host [172.27.116.67]
INFO[0035] Removing container [rke-log-cleaner] on host [172.27.116.67], try #1
INFO[0035] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.67]
DEBU[0035] [cleanup] Successfully cleaned up log links on host [172.27.116.67]
INFO[0035] [hosts] Successfully cleaned up host [172.27.116.67]
INFO[0035] [reconcile] Check etcd hosts to be added
DEBU[0035] [reconcile] Check worker hosts to be deleted
INFO[0035] [hosts] host [172.27.116.67] has another role, skipping delete from kubernetes cluster
INFO[0035] [worker] Tearing down Worker Plane..
INFO[0035] [worker] Host [172.27.116.67] is already a controlplane host, nothing to do.
INFO[0035] [worker] Successfully tore down Worker Plane..
INFO[0035] [hosts] Host [172.27.116.67] is already a controlplane or etcd host, skipping cleanup.
DEBU[0035] [reconcile] Check Control plane hosts to be deleted
INFO[0035] [hosts] Cordoning host [172.27.116.67]
DEBU[0035] Checking node list for node [ks-9047368], try #1
DEBU[0035] Checking node list for node [ks-9047368], try #1
DEBU[0035] Checking node list for node [ks-9047368], try #1
DEBU[0035] Node ks-9047368 is already cordoned: true
INFO[0035] [hosts] Deleting host [172.27.116.67] from the cluster
INFO[0035] [hosts] Successfully deleted host [172.27.116.67] from the cluster
INFO[0035] [controlplane] Tearing down the Controller Plane..
DEBU[0035] [remove/kube-apiserver] Checking if container is running on host [172.27.116.67]
DEBU[0035] [remove/kube-apiserver] Removing container on host [172.27.116.67]
INFO[0035] Removing container [kube-apiserver] on host [172.27.116.67], try #1
INFO[0039] [remove/kube-apiserver] Successfully removed container on host [172.27.116.67]
DEBU[0039] [remove/kube-controller-manager] Checking if container is running on host [172.27.116.67]
DEBU[0039] [remove/kube-controller-manager] Removing container on host [172.27.116.67]
INFO[0039] Removing container [kube-controller-manager] on host [172.27.116.67], try #1
INFO[0044] [remove/kube-controller-manager] Successfully removed container on host [172.27.116.67]
DEBU[0044] [remove/kube-scheduler] Checking if container is running on host [172.27.116.67]
DEBU[0044] [remove/kube-scheduler] Removing container on host [172.27.116.67]
INFO[0044] Removing container [kube-scheduler] on host [172.27.116.67], try #1
INFO[0048] [remove/kube-scheduler] Successfully removed container on host [172.27.116.67]
DEBU[0048] [remove/kubelet] Checking if container is running on host [172.27.116.67]
DEBU[0048] [remove/kubelet] Removing container on host [172.27.116.67]
INFO[0048] Removing container [kubelet] on host [172.27.116.67], try #1
INFO[0053] [remove/kubelet] Successfully removed container on host [172.27.116.67]
DEBU[0053] [remove/kube-proxy] Checking if container is running on host [172.27.116.67]
DEBU[0053] [remove/kube-proxy] Removing container on host [172.27.116.67]
INFO[0053] Removing container [kube-proxy] on host [172.27.116.67], try #1
INFO[0057] [remove/kube-proxy] Successfully removed container on host [172.27.116.67]
DEBU[0057] [remove/service-sidekick] Checking if container is running on host [172.27.116.67]
DEBU[0057] [remove/service-sidekick] Removing container on host [172.27.116.67]
INFO[0057] Removing container [service-sidekick] on host [172.27.116.67], try #1
INFO[0058] [remove/service-sidekick] Successfully removed container on host [172.27.116.67]
INFO[0058] [controlplane] Successfully tore down Controller Plane..
INFO[0058] [hosts] Cleaning up host [172.27.116.67]
DEBU[0058] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0058] [hosts] Running cleaner container on host [172.27.116.67]
DEBU[0058] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0058] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0059] Starting container [kube-cleaner] on host [172.27.116.67], try #1
INFO[0060] [kube-cleaner] Successfully started [kube-cleaner] container on host [172.27.116.67]
INFO[0060] Waiting for [kube-cleaner] container to exit on host [172.27.116.67]
DEBU[0061] Exit code for [kube-cleaner] container on host [172.27.116.67] is [0]
INFO[0061] [hosts] Removing cleaner container on host [172.27.116.67]
INFO[0061] Removing container [kube-cleaner] on host [172.27.116.67], try #1
INFO[0061] [hosts] Removing dead container logs on host [172.27.116.67]
DEBU[0061] [cleanup] Starting log link cleanup on host [172.27.116.67]
DEBU[0061] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.67]
DEBU[0061] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.67]
DEBU[0061] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0061] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0062] Starting container [rke-log-cleaner] on host [172.27.116.67], try #1
INFO[0064] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.67]
DEBU[0064] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.67]
DEBU[0064] [remove/rke-log-cleaner] Removing container on host [172.27.116.67]
INFO[0064] Removing container [rke-log-cleaner] on host [172.27.116.67], try #1
INFO[0065] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.67]
DEBU[0065] [cleanup] Successfully cleaned up log links on host [172.27.116.67]
INFO[0065] [hosts] Successfully cleaned up host [172.27.116.67]
INFO[0065] [reconcile] Rebuilding and updating local kube config
DEBU[0065] [reconcile] Rebuilding and updating local kube config, creating new kubeconfig
DEBU[0065] Deploying admin Kubeconfig locally at [./kube_config_cluster.yml]
INFO[0065] Successfully Deployed local admin kubeconfig at [./kube_config_cluster.yml]
DEBU[0065] [version] Using ./kube_config_cluster.yml to connect to Kubernetes cluster..
DEBU[0065] [version] Getting Kubernetes server version..
INFO[0065] [reconcile] host [172.27.116.65] is a control plane node with reachable Kubernetes API endpoint in the cluster
DEBU[0065] [restart/kube-apiserver] Checking if container is running on host [172.27.116.65]
DEBU[0065] [restart/kube-apiserver] Restarting container on host [172.27.116.65]
INFO[0065] Restarting container [kube-apiserver] on host [172.27.116.65], try #1
INFO[0074] [restart/kube-apiserver] Successfully restarted container on host [172.27.116.65]
DEBU[0074] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.65]
DEBU[0074] [restart/kube-controller-manager] Restarting container on host [172.27.116.65]
INFO[0074] Restarting container [kube-controller-manager] on host [172.27.116.65], try #1
INFO[0080] [restart/kube-controller-manager] Successfully restarted container on host [172.27.116.65]
DEBU[0080] [restart/kube-apiserver] Checking if container is running on host [172.27.116.66]
DEBU[0080] [restart/kube-apiserver] Restarting container on host [172.27.116.66]
INFO[0080] Restarting container [kube-apiserver] on host [172.27.116.66], try #1
INFO[0088] [restart/kube-apiserver] Successfully restarted container on host [172.27.116.66]
DEBU[0088] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.66]
DEBU[0088] [restart/kube-controller-manager] Restarting container on host [172.27.116.66]
INFO[0088] Restarting container [kube-controller-manager] on host [172.27.116.66], try #1
INFO[0091] [restart/kube-controller-manager] Successfully restarted container on host [172.27.116.66]
DEBU[0091] [restart/etcd] Checking if container is running on host [ks-9047489]
DEBU[0091] [restart/etcd] Restarting container on host [ks-9047489]
INFO[0091] Restarting container [etcd] on host [ks-9047489], try #1
INFO[0095] [restart/etcd] Successfully restarted container on host [ks-9047489]
DEBU[0095] [restart/etcd] Checking if container is running on host [ks-9047366]
DEBU[0095] [restart/etcd] Restarting container on host [ks-9047366]
INFO[0095] Restarting container [etcd] on host [ks-9047366], try #1
INFO[0099] [restart/etcd] Successfully restarted container on host [ks-9047366]
INFO[0099] [reconcile] Reconciled cluster state successfully
DEBU[0099] Provided value for maxUnavailable: {1 0 10%}
INFO[0099] max_unavailable_worker got rounded down to 0, resetting to 1
DEBU[0099] Parsed value of maxUnavailable: 1
DEBU[0099] Provided value for maxUnavailable: {0 1 }
DEBU[0099] Parsed value of maxUnavailable: 1
INFO[0099] Setting maxUnavailable for worker nodes to: 1
INFO[0099] Setting maxUnavailable for controlplane nodes to: 1
DEBU[0099] Encryption is disabled in both current and new spec; no action is required
INFO[0099] Pre-pulling kubernetes images
DEBU[0099] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65], try #1
DEBU[0099] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66], try #1
INFO[0099] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66]
INFO[0099] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65]
INFO[0099] Kubernetes images pulled successfully
DEBU[0099] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0099] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0099] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0099] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0099] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0099] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0099] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0099] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0099] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0099] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0099] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0099] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0099] [etcd] Building up etcd plane..
DEBU[0099] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0099] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0099] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0103] Starting container [etcd-fix-perm] on host [172.27.116.65], try #1
INFO[0106] Successfully started [etcd-fix-perm] container on host [172.27.116.65]
INFO[0106] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.65]
INFO[0106] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.65]
DEBU[0112] Exit code for [etcd-fix-perm] container on host [172.27.116.65] is [0]
DEBU[0112] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.65]
DEBU[0112] [remove/etcd-fix-perm] Removing container on host [172.27.116.65]
INFO[0112] Removing container [etcd-fix-perm] on host [172.27.116.65], try #1
INFO[0114] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.65]
DEBU[0115] [etcd] Container [etcd] is in a restarting loop [172.27.116.65]
INFO[0115] Restarting container [etcd] on host [172.27.116.65], try #1
DEBU[0120] [etcd] Container [etcd] is already running on host [172.27.116.65]
DEBU[0120] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.65]
DEBU[0120] slice is not equal, showing data in new value which is not in old value: map[--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380:{}]
DEBU[0120] slice is not equal, showing data in old value which is not in new value: map[--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380:{}]
DEBU[0120] [etcd] Container [etcd] is eligible for upgrade on host [172.27.116.65]
DEBU[0120] [etcd] Checking for deployed [etcd]
INFO[0120] Checking if container [etcd] is running on host [172.27.116.65], try #1
DEBU[0120] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.65], try #1
INFO[0120] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.65]
DEBU[0120] [etcd] Stopping old container
INFO[0120] Checking if container [old-etcd] is running on host [172.27.116.65], try #1
INFO[0120] Stopping container [etcd] on host [172.27.116.65] with stopTimeoutDuration [5s], try #1
INFO[0122] Waiting for [etcd] container to exit on host [172.27.116.65]
DEBU[0122] Exit code for [etcd] container on host [172.27.116.65] is [2]
INFO[0122] Renaming container [etcd] to [old-etcd] on host [172.27.116.65], try #1
DEBU[0122] [etcd] Successfully stopped old container etcd on host [172.27.116.65]
INFO[0125] Starting container [etcd] on host [172.27.116.65], try #1
INFO[0129] [etcd] Successfully updated [etcd] container on host [172.27.116.65]
DEBU[0129] [etcd] Removing old container
INFO[0129] Removing container [old-etcd] on host [172.27.116.65], try #1
DEBU[0130] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0130] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0130] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0130] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.65]
DEBU[0130] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.55:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0130] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.65]
DEBU[0130] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.65]
INFO[0130] Removing container [etcd-rolling-snapshots] on host [172.27.116.65], try #1
INFO[0132] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.65]
DEBU[0132] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0132] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
INFO[0133] Starting container [etcd-rolling-snapshots] on host [172.27.116.65], try #1
INFO[0134] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.65]
DEBU[0139] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0139] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0139] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
INFO[0141] Starting container [rke-bundle-cert] on host [172.27.116.65], try #1
INFO[0142] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.65]
INFO[0142] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.65]
DEBU[0144] Exit code for [rke-bundle-cert] container on host [172.27.116.65] is [0]
INFO[0144] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.65]
INFO[0144] Removing container [rke-bundle-cert] on host [172.27.116.65], try #1
DEBU[0144] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0144] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0144] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0144] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0144] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0146] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0149] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0149] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0151] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0151] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0152] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0152] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0152] [etcd] Creating log link for Container [etcd] on host [172.27.116.65]
DEBU[0153] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0153] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0153] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0153] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0154] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0156] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0156] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0157] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0157] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0158] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0158] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.65]
DEBU[0158] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0158] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0158] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0159] Starting container [etcd-fix-perm] on host [172.27.116.66], try #1
INFO[0162] Successfully started [etcd-fix-perm] container on host [172.27.116.66]
INFO[0162] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.66]
INFO[0162] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.66]
DEBU[0164] Exit code for [etcd-fix-perm] container on host [172.27.116.66] is [0]
DEBU[0164] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.66]
DEBU[0164] [remove/etcd-fix-perm] Removing container on host [172.27.116.66]
INFO[0164] Removing container [etcd-fix-perm] on host [172.27.116.66], try #1
INFO[0165] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.66]
DEBU[0165] [etcd] Container [etcd] is in a restarting loop [172.27.116.66]
INFO[0165] Restarting container [etcd] on host [172.27.116.66], try #1
DEBU[0168] [etcd] Container [etcd] is already running on host [172.27.116.66]
DEBU[0168] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.66]
DEBU[0168] slice is not equal, showing data in new value which is not in old value: map[--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380:{}]
DEBU[0168] slice is not equal, showing data in old value which is not in new value: map[--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380:{}]
DEBU[0168] [etcd] Container [etcd] is eligible for upgrade on host [172.27.116.66]
DEBU[0168] [etcd] Checking for deployed [etcd]
INFO[0168] Checking if container [etcd] is running on host [172.27.116.66], try #1
DEBU[0168] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.66], try #1
INFO[0168] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.66]
DEBU[0168] [etcd] Stopping old container
INFO[0168] Checking if container [old-etcd] is running on host [172.27.116.66], try #1
INFO[0168] Stopping container [etcd] on host [172.27.116.66] with stopTimeoutDuration [5s], try #1
INFO[0169] Waiting for [etcd] container to exit on host [172.27.116.66]
DEBU[0169] Exit code for [etcd] container on host [172.27.116.66] is [2]
INFO[0169] Renaming container [etcd] to [old-etcd] on host [172.27.116.66], try #1
DEBU[0169] [etcd] Successfully stopped old container etcd on host [172.27.116.66]
INFO[0170] Starting container [etcd] on host [172.27.116.66], try #1
INFO[0173] [etcd] Successfully updated [etcd] container on host [172.27.116.66]
DEBU[0173] [etcd] Removing old container
INFO[0173] Removing container [old-etcd] on host [172.27.116.66], try #1
DEBU[0173] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0173] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0173] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0173] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.66]
DEBU[0173] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.56:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0173] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.66]
DEBU[0173] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.66]
INFO[0173] Removing container [etcd-rolling-snapshots] on host [172.27.116.66], try #1
INFO[0176] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.66]
DEBU[0176] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0176] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
INFO[0179] Starting container [etcd-rolling-snapshots] on host [172.27.116.66], try #1
INFO[0181] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.66]
DEBU[0186] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0186] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0186] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
INFO[0187] Starting container [rke-bundle-cert] on host [172.27.116.66], try #1
INFO[0190] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.66]
INFO[0190] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.66]
DEBU[0192] Exit code for [rke-bundle-cert] container on host [172.27.116.66] is [0]
INFO[0192] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.66]
INFO[0192] Removing container [rke-bundle-cert] on host [172.27.116.66], try #1
DEBU[0193] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0193] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0193] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0193] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0193] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0194] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0197] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0197] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0198] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0198] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0199] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0199] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0199] [etcd] Creating log link for Container [etcd] on host [172.27.116.66]
DEBU[0200] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0200] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0200] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0200] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0202] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0204] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0204] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0206] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0206] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0207] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0207] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.66]
INFO[0207] [etcd] Successfully started etcd plane.. Checking etcd cluster health
DEBU[0207] [etcd] check etcd cluster health on host [172.27.116.65]
DEBU[0207] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0212] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0217] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0222] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0227] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0232] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0237] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0243] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0248] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0253] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0258] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0264] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": EOF
DEBU[0269] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0274] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0279] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0284] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0289] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0294] [etcd] failed to check health for etcd host [172.27.116.65]: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
WARN[0299] [etcd] host [172.27.116.65] failed to check etcd health: failed to get /health for host [172.27.116.65]: Get "https://172.27.116.55:2379/health": Unable to access the service on 172.27.116.55:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0299] [etcd] check etcd cluster health on host [172.27.116.66]
DEBU[0300] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0305] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0312] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": EOF
DEBU[0317] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0322] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0327] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0332] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0337] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0342] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0347] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0352] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0358] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0363] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0368] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0374] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": EOF
DEBU[0379] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0385] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
DEBU[0390] [etcd] failed to check health for etcd host [172.27.116.66]: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
WARN[0395] [etcd] host [172.27.116.66] failed to check etcd health: failed to get /health for host [172.27.116.66]: Get "https://172.27.116.56:2379/health": Unable to access the service on 172.27.116.56:2379. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused)
FATA[0395] [etcd] Failed to bring up Etcd Plane: etcd cluster is unhealthy: hosts [172.27.116.65,172.27.116.66] failed to report healthy. Check etcd container logs on each host for more information
root@ks-9047489:~#
```  

The etcd containers(node 65, 66) in the cluster are always restarting.  
```sh  
root@ks-9047366:~# docker ps -a|grep -E 'kube-|etcd'
7ec3a65360a5   rancher/rke-tools:v0.1.80                          "/docker-entrypoint.…"   7 minutes ago        Up 7 minutes                              etcd-rolling-snapshots
9b84de56b18d   rancher/mirrored-coreos-etcd:v3.5.0                "/usr/local/bin/etcd…"   7 minutes ago        Restarting (2) 14 seconds ago             etcd
2a8174bfb7a7   rancher/hyperkube:v1.22.10-rancher1                "/opt/rke-tools/entr…"   34 minutes ago       Up 1 second                               kube-apiserver
5f19b4e05409   e6ea68648f0c                                       "/opt/bin/flanneld -…"   23 hours ago         Up 23 hours                               k8s_kube-flannel_kube-flannel-hdqpn_kube-system_25d73a12-3d85-4a86-9325-aec7fc6f36e5_3
af53c740af00   204d7aaf689a                                       "/install-cni.sh"        23 hours ago         Up 23 hours                               k8s_install-cni_kube-flannel-hdqpn_kube-system_25d73a12-3d85-4a86-9325-aec7fc6f36e5_3
f8af8d9544bb   rancher/mirrored-pause:3.6                         "/pause"                 23 hours ago         Up 23 hours                               k8s_POD_kube-flannel-hdqpn_kube-system_25d73a12-3d85-4a86-9325-aec7fc6f36e5_3
df5f24e8f37b   e6ea68648f0c                                       "/opt/bin/flanneld -…"   2 days ago           Exited (255) 23 hours ago                 k8s_kube-flannel_kube-flannel-hdqpn_kube-system_25d73a12-3d85-4a86-9325-aec7fc6f36e5_2
0893db2b9716   204d7aaf689a                                       "/install-cni.sh"        2 days ago           Exited (255) 23 hours ago                 k8s_install-cni_kube-flannel-hdqpn_kube-system_25d73a12-3d85-4a86-9325-aec7fc6f36e5_2
64bb9d16ef4c   rancher/mirrored-pause:3.6                         "/pause"                 2 days ago           Exited (255) 23 hours ago                 k8s_POD_kube-flannel-hdqpn_kube-system_25d73a12-3d85-4a86-9325-aec7fc6f36e5_2
f0d9c86e9d02   rancher/hyperkube:v1.22.10-rancher1                "/opt/rke-tools/entr…"   7 days ago           Up 23 hours                               kube-proxy
cd2f70b07c76   rancher/hyperkube:v1.22.10-rancher1                "/opt/rke-tools/entr…"   7 days ago           Up 34 minutes                             kube-scheduler
750db7f84f04   rancher/hyperkube:v1.22.10-rancher1                "/opt/rke-tools/entr…"   7 days ago           Up 1 second                               kube-controller-manager
```  
The etcd container log  
```sh  
root@ks-9047366:~# docker logs -n 500 etcd
{"level":"info","ts":"2023-02-22T08:21:08.180Z","caller":"rafthttp/transport.go:317","msg":"added remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28","remote-peer-urls":["https://172.27.116.55:2380"]}
{"level":"info","ts":"2023-02-22T08:21:08.180Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:21:08.180Z","caller":"etcdserver/server.go:834","msg":"starting etcd server","local-member-id":"55e70c89f36a763b","local-server-version":"3.5.0","cluster-id":"bb159e7ec69bb5bc","cluster-version":"3.5"}
{"level":"info","ts":"2023-02-22T08:21:08.182Z","caller":"etcdserver/server.go:744","msg":"starting initial election tick advance","election-ticks":10}
{"level":"info","ts":"2023-02-22T08:21:08.185Z","caller":"embed/etcd.go:687","msg":"starting with client TLS","tls-info":"cert = /etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem, key = /etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem, client-cert=, client-key=, trusted-ca = /etc/kubernetes/ssl/kube-ca.pem, client-cert-auth = true, crl-file = ","cipher-suites":["TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256","TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384"]}
{"level":"info","ts":"2023-02-22T08:21:08.185Z","caller":"embed/etcd.go:276","msg":"now serving peer/client/metrics","local-member-id":"55e70c89f36a763b","initial-advertise-peer-urls":["https://172.27.116.56:2380"],"listen-peer-urls":["https://172.27.116.56:2380"],"advertise-client-urls":["https://172.27.116.56:2379"],"listen-client-urls":["https://172.27.116.56:2379"],"listen-metrics-urls":[]}
{"level":"info","ts":"2023-02-22T08:21:08.185Z","caller":"embed/etcd.go:580","msg":"serving peer traffic","address":"172.27.116.56:2380"}
{"level":"info","ts":"2023-02-22T08:21:08.185Z","caller":"embed/etcd.go:552","msg":"cmux::serve","address":"172.27.116.56:2380"}
{"level":"info","ts":"2023-02-22T08:21:08.279Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5021471102415353739 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:21:08.280Z","caller":"membership/cluster.go:393","msg":"added member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","added-peer-id":"45afd95cdd5b378b","added-peer-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:21:08.280Z","caller":"rafthttp/peer.go:133","msg":"starting remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.280Z","caller":"rafthttp/pipeline.go:72","msg":"started HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.280Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.281Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.281Z","caller":"rafthttp/peer.go:137","msg":"started remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.281Z","caller":"rafthttp/transport.go:317","msg":"added remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b","remote-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:21:08.281Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.281Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"warn","ts":"2023-02-22T08:21:08.286Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"warn","ts":"2023-02-22T08:21:08.290Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"info","ts":"2023-02-22T08:21:08.399Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:21:08.399Z","caller":"membership/cluster.go:419","msg":"removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"45afd95cdd5b378b","removed-remote-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:21:08.399Z","caller":"rafthttp/peer.go:330","msg":"stopping remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.399Z","caller":"rafthttp/stream.go:294","msg":"stopped TCP streaming connection with remote peer","stream-writer-type":"unknown stream","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.399Z","caller":"rafthttp/stream.go:294","msg":"stopped TCP streaming connection with remote peer","stream-writer-type":"unknown stream","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.400Z","caller":"rafthttp/pipeline.go:85","msg":"stopped HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.400Z","caller":"rafthttp/stream.go:442","msg":"stopped stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.400Z","caller":"rafthttp/stream.go:442","msg":"stopped stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.400Z","caller":"rafthttp/peer.go:335","msg":"stopped remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:21:08.400Z","caller":"rafthttp/transport.go:355","msg":"removed remote peer","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"45afd95cdd5b378b"}
{"level":"warn","ts":"2023-02-22T08:21:08.405Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"warn","ts":"2023-02-22T08:21:08.409Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"info","ts":"2023-02-22T08:21:08.475Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(5486964048988609832 6189929999477929531)"}
{"level":"warn","ts":"2023-02-22T08:21:08.475Z","caller":"membership/cluster.go:427","msg":"skipped removing already removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"21cea6a99b09da5b"}
{"level":"panic","ts":"2023-02-22T08:21:08.475Z","caller":"rafthttp/transport.go:346","msg":"unexpected removal of unknown remote peer","remote-peer-id":"21cea6a99b09da5b","stacktrace":"go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).removePeer\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:346\ngo.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).RemovePeer\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:329\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyConfChange\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2301\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).apply\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2133\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyEntries\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1357\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyAll\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1179\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).run.func8\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1111\ngo.etcd.io/etcd/pkg/v3/schedule.(*fifo).run\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:157"}
panic: unexpected removal of unknown remote peer

goroutine 257 [running]:
go.uber.org/zap/zapcore.(*CheckedEntry).Write(0xc00ac52180, 0xc00753d340, 0x1, 0x1)
        /home/remote/sbatsche/.gvm/pkgsets/go1.16.3/global/pkg/mod/go.uber.org/zap@v1.17.0/zapcore/entry.go:234 +0x58d
go.uber.org/zap.(*Logger).Panic(0xc00060e8c0, 0x122d9ab, 0x29, 0xc00753d340, 0x1, 0x1)
        /home/remote/sbatsche/.gvm/pkgsets/go1.16.3/global/pkg/mod/go.uber.org/zap@v1.17.0/logger.go:227 +0x85
go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).removePeer(0xc0004bca80, 0x21cea6a99b09da5b)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:346 +0x58c
go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).RemovePeer(0xc0004bca80, 0x21cea6a99b09da5b)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:329 +0x7d
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyConfChange(0xc0004ee700, 0x1, 0x21cea6a99b09da5b, 0x0, 0x0, 0x0, 0x1d28867813ec3c0e, 0xc009018000, 0x0, 0x0, ...)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2301 +0x872
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).apply(0xc0004ee700, 0xc007d1daf0, 0x1ff, 0x2c5, 0xc009018000, 0xc0083f0e98, 0xc0083f0e50, 0xc705fd)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2133 +0x59a
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyEntries(0xc0004ee700, 0xc009018000, 0xc009198fd0)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1357 +0xe5
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyAll(0xc0004ee700, 0xc009018000, 0xc009198fd0)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1179 +0x88
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).run.func8(0x1399c10, 0xc0034fe040)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1111 +0x3c
go.etcd.io/etcd/pkg/v3/schedule.(*fifo).run(0xc000162000)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:157 +0xf3
created by go.etcd.io/etcd/pkg/v3/schedule.NewFIFOScheduler
        /tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:70 +0x13b
{"level":"warn","ts":1677054129.1104665,"caller":"flags/flag.go:93","msg":"unrecognized environment variable","environment-variable":"ETCD_UNSUPPORTED_ARCH=x86_64"}
{"level":"info","ts":"2023-02-22T08:22:09.110Z","caller":"etcdmain/etcd.go:72","msg":"Running: ","args":["/usr/local/bin/etcd","--name=etcd-ks-9047366","--listen-client-urls=https://172.27.116.56:2379","--initial-advertise-peer-urls=https://172.27.116.56:2380","--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380","--client-cert-auth=true","--data-dir=/var/lib/rancher/etcd/","--peer-trusted-ca-file=/etc/kubernetes/ssl/kube-ca.pem","--key-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem","--peer-cert-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem","--peer-key-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem","--election-timeout=5000","--heartbeat-interval=500","--initial-cluster-token=etcd-cluster-1","--trusted-ca-file=/etc/kubernetes/ssl/kube-ca.pem","--advertise-client-urls=https://172.27.116.56:2379","--cipher-suites=TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384","--peer-client-cert-auth=true","--listen-peer-urls=https://172.27.116.56:2380","--cert-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem","--initial-cluster-state=new"]}
{"level":"info","ts":"2023-02-22T08:22:09.110Z","caller":"etcdmain/etcd.go:115","msg":"server has been already initialized","data-dir":"/var/lib/rancher/etcd/","dir-type":"member"}
{"level":"info","ts":"2023-02-22T08:22:09.110Z","caller":"embed/etcd.go:131","msg":"configuring peer listeners","listen-peer-urls":["https://172.27.116.56:2380"]}
{"level":"info","ts":"2023-02-22T08:22:09.110Z","caller":"embed/etcd.go:478","msg":"starting with peer TLS","tls-info":"cert = /etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem, key = /etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem, client-cert=, client-key=, trusted-ca = /etc/kubernetes/ssl/kube-ca.pem, client-cert-auth = true, crl-file = ","cipher-suites":["TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256","TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384"]}
{"level":"info","ts":"2023-02-22T08:22:09.112Z","caller":"embed/etcd.go:139","msg":"configuring client listeners","listen-client-urls":["https://172.27.116.56:2379"]}
{"level":"info","ts":"2023-02-22T08:22:09.112Z","caller":"embed/etcd.go:307","msg":"starting an etcd server","etcd-version":"3.5.0","git-sha":"946a5a6f2","go-version":"go1.16.3","go-os":"linux","go-arch":"amd64","max-cpu-set":23,"max-cpu-available":23,"member-initialized":true,"name":"etcd-ks-9047366","data-dir":"/var/lib/rancher/etcd/","wal-dir":"","wal-dir-dedicated":"","member-dir":"/var/lib/rancher/etcd/member","force-new-cluster":false,"heartbeat-interval":"500ms","election-timeout":"5s","initial-election-tick-advance":true,"snapshot-count":100000,"snapshot-catchup-entries":5000,"initial-advertise-peer-urls":["https://172.27.116.56:2380"],"listen-peer-urls":["https://172.27.116.56:2380"],"advertise-client-urls":["https://172.27.116.56:2379"],"listen-client-urls":["https://172.27.116.56:2379"],"listen-metrics-urls":[],"cors":["*"],"host-whitelist":["*"],"initial-cluster":"","initial-cluster-state":"new","initial-cluster-token":"","quota-size-bytes":2147483648,"pre-vote":true,"initial-corrupt-check":false,"corrupt-check-time-interval":"0s","auto-compaction-mode":"periodic","auto-compaction-retention":"0s","auto-compaction-interval":"0s","discovery-url":"","discovery-proxy":"","downgrade-check-interval":"5s"}
{"level":"info","ts":"2023-02-22T08:22:09.148Z","caller":"etcdserver/backend.go:81","msg":"opened backend db","path":"/var/lib/rancher/etcd/member/snap/db","took":"35.219341ms"}
{"level":"info","ts":"2023-02-22T08:22:09.874Z","caller":"etcdserver/server.go:508","msg":"recovered v2 store from snapshot","snapshot-index":4982658,"snapshot-size":"12 kB"}
{"level":"info","ts":"2023-02-22T08:22:09.874Z","caller":"etcdserver/server.go:518","msg":"recovered v3 backend from snapshot","backend-size-bytes":57573376,"backend-size":"58 MB","backend-size-in-use-bytes":44036096,"backend-size-in-use":"44 MB"}
{"level":"info","ts":"2023-02-22T08:22:10.356Z","caller":"etcdserver/raft.go:483","msg":"restarting local member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","commit-index":5037561}
{"level":"info","ts":"2023-02-22T08:22:10.359Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:22:10.359Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b became follower at term 17"}
{"level":"info","ts":"2023-02-22T08:22:10.359Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"newRaft 55e70c89f36a763b [peers: [21cea6a99b09da5b,4c259cbb3b4e1d28,55e70c89f36a763b], term: 17, commit: 5037561, applied: 4982658, lastindex: 5037564, lastterm: 17]"}
{"level":"info","ts":"2023-02-22T08:22:10.359Z","caller":"api/capability.go:75","msg":"enabled capabilities for version","cluster-version":"3.5"}
{"level":"info","ts":"2023-02-22T08:22:10.359Z","caller":"membership/cluster.go:276","msg":"recovered/added member from store","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","recovered-remote-peer-id":"4c259cbb3b4e1d28","recovered-remote-peer-urls":["https://172.27.116.55:2380"]}
{"level":"info","ts":"2023-02-22T08:22:10.359Z","caller":"membership/cluster.go:276","msg":"recovered/added member from store","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","recovered-remote-peer-id":"55e70c89f36a763b","recovered-remote-peer-urls":["https://172.27.116.56:2380"]}
{"level":"info","ts":"2023-02-22T08:22:10.359Z","caller":"membership/cluster.go:285","msg":"set cluster version from store","cluster-version":"3.5"}
{"level":"warn","ts":"2023-02-22T08:22:10.379Z","caller":"auth/store.go:1220","msg":"simple token is not cryptographically signed"}
{"level":"info","ts":"2023-02-22T08:22:10.388Z","caller":"mvcc/kvstore.go:345","msg":"restored last compact revision","meta-bucket-name":"meta","meta-bucket-name-key":"finishedCompactRev","restored-compact-revision":4603957}
{"level":"info","ts":"2023-02-22T08:22:10.460Z","caller":"mvcc/kvstore.go:415","msg":"kvstore restored","current-rev":4606139}
{"level":"info","ts":"2023-02-22T08:22:10.516Z","caller":"etcdserver/quota.go:94","msg":"enabled backend quota with default value","quota-name":"v3-applier","quota-size-bytes":2147483648,"quota-size":"2.1 GB"}
{"level":"info","ts":"2023-02-22T08:22:10.525Z","caller":"rafthttp/peer.go:133","msg":"starting remote peer","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:22:10.525Z","caller":"rafthttp/pipeline.go:72","msg":"started HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:22:10.525Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:22:10.526Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:22:10.526Z","caller":"rafthttp/peer.go:137","msg":"started remote peer","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:22:10.526Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:22:10.526Z","caller":"rafthttp/transport.go:317","msg":"added remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28","remote-peer-urls":["https://172.27.116.55:2380"]}
{"level":"info","ts":"2023-02-22T08:22:10.526Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:22:10.526Z","caller":"etcdserver/server.go:834","msg":"starting etcd server","local-member-id":"55e70c89f36a763b","local-server-version":"3.5.0","cluster-id":"bb159e7ec69bb5bc","cluster-version":"3.5"}
{"level":"info","ts":"2023-02-22T08:22:10.526Z","caller":"etcdserver/server.go:744","msg":"starting initial election tick advance","election-ticks":10}
{"level":"info","ts":"2023-02-22T08:22:10.530Z","caller":"embed/etcd.go:687","msg":"starting with client TLS","tls-info":"cert = /etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem, key = /etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem, client-cert=, client-key=, trusted-ca = /etc/kubernetes/ssl/kube-ca.pem, client-cert-auth = true, crl-file = ","cipher-suites":["TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256","TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384"]}
{"level":"info","ts":"2023-02-22T08:22:10.530Z","caller":"embed/etcd.go:276","msg":"now serving peer/client/metrics","local-member-id":"55e70c89f36a763b","initial-advertise-peer-urls":["https://172.27.116.56:2380"],"listen-peer-urls":["https://172.27.116.56:2380"],"advertise-client-urls":["https://172.27.116.56:2379"],"listen-client-urls":["https://172.27.116.56:2379"],"listen-metrics-urls":[]}
{"level":"info","ts":"2023-02-22T08:22:10.531Z","caller":"embed/etcd.go:580","msg":"serving peer traffic","address":"172.27.116.56:2380"}
{"level":"info","ts":"2023-02-22T08:22:10.531Z","caller":"embed/etcd.go:552","msg":"cmux::serve","address":"172.27.116.56:2380"}
{"level":"info","ts":"2023-02-22T08:22:10.618Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5021471102415353739 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:22:10.619Z","caller":"membership/cluster.go:393","msg":"added member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","added-peer-id":"45afd95cdd5b378b","added-peer-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:22:10.619Z","caller":"rafthttp/peer.go:133","msg":"starting remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.619Z","caller":"rafthttp/pipeline.go:72","msg":"started HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.619Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.621Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.624Z","caller":"rafthttp/peer.go:137","msg":"started remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.624Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.624Z","caller":"rafthttp/transport.go:317","msg":"added remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b","remote-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:22:10.625Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"warn","ts":"2023-02-22T08:22:10.630Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"warn","ts":"2023-02-22T08:22:10.634Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"info","ts":"2023-02-22T08:22:10.753Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:22:10.753Z","caller":"membership/cluster.go:419","msg":"removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"45afd95cdd5b378b","removed-remote-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:22:10.753Z","caller":"rafthttp/peer.go:330","msg":"stopping remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.753Z","caller":"rafthttp/stream.go:294","msg":"stopped TCP streaming connection with remote peer","stream-writer-type":"unknown stream","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.753Z","caller":"rafthttp/stream.go:294","msg":"stopped TCP streaming connection with remote peer","stream-writer-type":"unknown stream","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.753Z","caller":"rafthttp/pipeline.go:85","msg":"stopped HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.753Z","caller":"rafthttp/stream.go:442","msg":"stopped stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.754Z","caller":"rafthttp/stream.go:442","msg":"stopped stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.754Z","caller":"rafthttp/peer.go:335","msg":"stopped remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:22:10.754Z","caller":"rafthttp/transport.go:355","msg":"removed remote peer","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"45afd95cdd5b378b"}
{"level":"warn","ts":"2023-02-22T08:22:10.762Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"warn","ts":"2023-02-22T08:22:10.767Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"info","ts":"2023-02-22T08:22:10.841Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(5486964048988609832 6189929999477929531)"}
{"level":"warn","ts":"2023-02-22T08:22:10.841Z","caller":"membership/cluster.go:427","msg":"skipped removing already removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"21cea6a99b09da5b"}
{"level":"panic","ts":"2023-02-22T08:22:10.841Z","caller":"rafthttp/transport.go:346","msg":"unexpected removal of unknown remote peer","remote-peer-id":"21cea6a99b09da5b","stacktrace":"go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).removePeer\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:346\ngo.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).RemovePeer\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:329\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyConfChange\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2301\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).apply\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2133\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyEntries\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1357\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyAll\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1179\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).run.func8\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1111\ngo.etcd.io/etcd/pkg/v3/schedule.(*fifo).run\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:157"}
panic: unexpected removal of unknown remote peer

goroutine 138 [running]:
go.uber.org/zap/zapcore.(*CheckedEntry).Write(0xc0081900c0, 0xc006f9e500, 0x1, 0x1)
        /home/remote/sbatsche/.gvm/pkgsets/go1.16.3/global/pkg/mod/go.uber.org/zap@v1.17.0/zapcore/entry.go:234 +0x58d
go.uber.org/zap.(*Logger).Panic(0xc00083d590, 0x122d9ab, 0x29, 0xc006f9e500, 0x1, 0x1)
        /home/remote/sbatsche/.gvm/pkgsets/go1.16.3/global/pkg/mod/go.uber.org/zap@v1.17.0/logger.go:227 +0x85
go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).removePeer(0xc0004f8a80, 0x21cea6a99b09da5b)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:346 +0x58c
go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).RemovePeer(0xc0004f8a80, 0x21cea6a99b09da5b)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:329 +0x7d
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyConfChange(0xc000491100, 0x1, 0x21cea6a99b09da5b, 0x0, 0x0, 0x0, 0x1d28867813ec3c0e, 0xc008200200, 0x0, 0x0, ...)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2301 +0x872
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).apply(0xc000491100, 0xc007b9daf0, 0x1ff, 0x2c5, 0xc008200200, 0xc0053bce38, 0xc0053bcdf0, 0xc705fd)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2133 +0x59a
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyEntries(0xc000491100, 0xc008200200, 0xc0053e0dc0)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1357 +0xe5
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyAll(0xc000491100, 0xc008200200, 0xc0053e0dc0)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1179 +0x88
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).run.func8(0x1399c10, 0xc0074f4140)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1111 +0x3c
go.etcd.io/etcd/pkg/v3/schedule.(*fifo).run(0xc0000b3500)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:157 +0xf3
created by go.etcd.io/etcd/pkg/v3/schedule.NewFIFOScheduler
        /tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:70 +0x13b
{"level":"warn","ts":1677054191.5684237,"caller":"flags/flag.go:93","msg":"unrecognized environment variable","environment-variable":"ETCD_UNSUPPORTED_ARCH=x86_64"}
{"level":"info","ts":"2023-02-22T08:23:11.568Z","caller":"etcdmain/etcd.go:72","msg":"Running: ","args":["/usr/local/bin/etcd","--name=etcd-ks-9047366","--listen-client-urls=https://172.27.116.56:2379","--initial-advertise-peer-urls=https://172.27.116.56:2380","--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380","--client-cert-auth=true","--data-dir=/var/lib/rancher/etcd/","--peer-trusted-ca-file=/etc/kubernetes/ssl/kube-ca.pem","--key-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem","--peer-cert-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem","--peer-key-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem","--election-timeout=5000","--heartbeat-interval=500","--initial-cluster-token=etcd-cluster-1","--trusted-ca-file=/etc/kubernetes/ssl/kube-ca.pem","--advertise-client-urls=https://172.27.116.56:2379","--cipher-suites=TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384","--peer-client-cert-auth=true","--listen-peer-urls=https://172.27.116.56:2380","--cert-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem","--initial-cluster-state=new"]}
{"level":"info","ts":"2023-02-22T08:23:11.568Z","caller":"etcdmain/etcd.go:115","msg":"server has been already initialized","data-dir":"/var/lib/rancher/etcd/","dir-type":"member"}
{"level":"info","ts":"2023-02-22T08:23:11.568Z","caller":"embed/etcd.go:131","msg":"configuring peer listeners","listen-peer-urls":["https://172.27.116.56:2380"]}
{"level":"info","ts":"2023-02-22T08:23:11.568Z","caller":"embed/etcd.go:478","msg":"starting with peer TLS","tls-info":"cert = /etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem, key = /etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem, client-cert=, client-key=, trusted-ca = /etc/kubernetes/ssl/kube-ca.pem, client-cert-auth = true, crl-file = ","cipher-suites":["TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256","TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384"]}
{"level":"info","ts":"2023-02-22T08:23:11.569Z","caller":"embed/etcd.go:139","msg":"configuring client listeners","listen-client-urls":["https://172.27.116.56:2379"]}
{"level":"info","ts":"2023-02-22T08:23:11.570Z","caller":"embed/etcd.go:307","msg":"starting an etcd server","etcd-version":"3.5.0","git-sha":"946a5a6f2","go-version":"go1.16.3","go-os":"linux","go-arch":"amd64","max-cpu-set":23,"max-cpu-available":23,"member-initialized":true,"name":"etcd-ks-9047366","data-dir":"/var/lib/rancher/etcd/","wal-dir":"","wal-dir-dedicated":"","member-dir":"/var/lib/rancher/etcd/member","force-new-cluster":false,"heartbeat-interval":"500ms","election-timeout":"5s","initial-election-tick-advance":true,"snapshot-count":100000,"snapshot-catchup-entries":5000,"initial-advertise-peer-urls":["https://172.27.116.56:2380"],"listen-peer-urls":["https://172.27.116.56:2380"],"advertise-client-urls":["https://172.27.116.56:2379"],"listen-client-urls":["https://172.27.116.56:2379"],"listen-metrics-urls":[],"cors":["*"],"host-whitelist":["*"],"initial-cluster":"","initial-cluster-state":"new","initial-cluster-token":"","quota-size-bytes":2147483648,"pre-vote":true,"initial-corrupt-check":false,"corrupt-check-time-interval":"0s","auto-compaction-mode":"periodic","auto-compaction-retention":"0s","auto-compaction-interval":"0s","discovery-url":"","discovery-proxy":"","downgrade-check-interval":"5s"}
{"level":"info","ts":"2023-02-22T08:23:11.611Z","caller":"etcdserver/backend.go:81","msg":"opened backend db","path":"/var/lib/rancher/etcd/member/snap/db","took":"40.762443ms"}
{"level":"info","ts":"2023-02-22T08:23:12.316Z","caller":"etcdserver/server.go:508","msg":"recovered v2 store from snapshot","snapshot-index":4982658,"snapshot-size":"12 kB"}
{"level":"info","ts":"2023-02-22T08:23:12.316Z","caller":"etcdserver/server.go:518","msg":"recovered v3 backend from snapshot","backend-size-bytes":57573376,"backend-size":"58 MB","backend-size-in-use-bytes":44036096,"backend-size-in-use":"44 MB"}
{"level":"info","ts":"2023-02-22T08:23:12.776Z","caller":"etcdserver/raft.go:483","msg":"restarting local member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","commit-index":5037561}
{"level":"info","ts":"2023-02-22T08:23:12.781Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:23:12.782Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b became follower at term 17"}
{"level":"info","ts":"2023-02-22T08:23:12.782Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"newRaft 55e70c89f36a763b [peers: [21cea6a99b09da5b,4c259cbb3b4e1d28,55e70c89f36a763b], term: 17, commit: 5037561, applied: 4982658, lastindex: 5037564, lastterm: 17]"}
{"level":"info","ts":"2023-02-22T08:23:12.782Z","caller":"api/capability.go:75","msg":"enabled capabilities for version","cluster-version":"3.5"}
{"level":"info","ts":"2023-02-22T08:23:12.782Z","caller":"membership/cluster.go:276","msg":"recovered/added member from store","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","recovered-remote-peer-id":"4c259cbb3b4e1d28","recovered-remote-peer-urls":["https://172.27.116.55:2380"]}
{"level":"info","ts":"2023-02-22T08:23:12.782Z","caller":"membership/cluster.go:276","msg":"recovered/added member from store","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","recovered-remote-peer-id":"55e70c89f36a763b","recovered-remote-peer-urls":["https://172.27.116.56:2380"]}
{"level":"info","ts":"2023-02-22T08:23:12.782Z","caller":"membership/cluster.go:285","msg":"set cluster version from store","cluster-version":"3.5"}
{"level":"warn","ts":"2023-02-22T08:23:12.808Z","caller":"auth/store.go:1220","msg":"simple token is not cryptographically signed"}
{"level":"info","ts":"2023-02-22T08:23:12.816Z","caller":"mvcc/kvstore.go:345","msg":"restored last compact revision","meta-bucket-name":"meta","meta-bucket-name-key":"finishedCompactRev","restored-compact-revision":4603957}
{"level":"info","ts":"2023-02-22T08:23:12.885Z","caller":"mvcc/kvstore.go:415","msg":"kvstore restored","current-rev":4606139}
{"level":"info","ts":"2023-02-22T08:23:12.897Z","caller":"etcdserver/quota.go:94","msg":"enabled backend quota with default value","quota-name":"v3-applier","quota-size-bytes":2147483648,"quota-size":"2.1 GB"}
{"level":"info","ts":"2023-02-22T08:23:12.906Z","caller":"rafthttp/peer.go:133","msg":"starting remote peer","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:23:12.906Z","caller":"rafthttp/pipeline.go:72","msg":"started HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:23:12.906Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:23:12.907Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:23:12.907Z","caller":"rafthttp/peer.go:137","msg":"started remote peer","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:23:12.907Z","caller":"rafthttp/transport.go:317","msg":"added remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28","remote-peer-urls":["https://172.27.116.55:2380"]}
{"level":"info","ts":"2023-02-22T08:23:12.907Z","caller":"etcdserver/server.go:834","msg":"starting etcd server","local-member-id":"55e70c89f36a763b","local-server-version":"3.5.0","cluster-id":"bb159e7ec69bb5bc","cluster-version":"3.5"}
{"level":"info","ts":"2023-02-22T08:23:12.907Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:23:12.908Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:23:12.908Z","caller":"etcdserver/server.go:744","msg":"starting initial election tick advance","election-ticks":10}
{"level":"info","ts":"2023-02-22T08:23:12.911Z","caller":"embed/etcd.go:687","msg":"starting with client TLS","tls-info":"cert = /etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem, key = /etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem, client-cert=, client-key=, trusted-ca = /etc/kubernetes/ssl/kube-ca.pem, client-cert-auth = true, crl-file = ","cipher-suites":["TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256","TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384"]}
{"level":"info","ts":"2023-02-22T08:23:12.911Z","caller":"embed/etcd.go:276","msg":"now serving peer/client/metrics","local-member-id":"55e70c89f36a763b","initial-advertise-peer-urls":["https://172.27.116.56:2380"],"listen-peer-urls":["https://172.27.116.56:2380"],"advertise-client-urls":["https://172.27.116.56:2379"],"listen-client-urls":["https://172.27.116.56:2379"],"listen-metrics-urls":[]}
{"level":"info","ts":"2023-02-22T08:23:12.911Z","caller":"embed/etcd.go:580","msg":"serving peer traffic","address":"172.27.116.56:2380"}
{"level":"info","ts":"2023-02-22T08:23:12.911Z","caller":"embed/etcd.go:552","msg":"cmux::serve","address":"172.27.116.56:2380"}
{"level":"info","ts":"2023-02-22T08:23:13.005Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5021471102415353739 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:23:13.006Z","caller":"membership/cluster.go:393","msg":"added member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","added-peer-id":"45afd95cdd5b378b","added-peer-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:23:13.006Z","caller":"rafthttp/peer.go:133","msg":"starting remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.006Z","caller":"rafthttp/pipeline.go:72","msg":"started HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.006Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.007Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.007Z","caller":"rafthttp/peer.go:137","msg":"started remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.007Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.007Z","caller":"rafthttp/transport.go:317","msg":"added remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b","remote-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:23:13.007Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"warn","ts":"2023-02-22T08:23:13.011Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"warn","ts":"2023-02-22T08:23:13.014Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"info","ts":"2023-02-22T08:23:13.119Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:23:13.119Z","caller":"membership/cluster.go:419","msg":"removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"45afd95cdd5b378b","removed-remote-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:23:13.119Z","caller":"rafthttp/peer.go:330","msg":"stopping remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.119Z","caller":"rafthttp/stream.go:294","msg":"stopped TCP streaming connection with remote peer","stream-writer-type":"unknown stream","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.119Z","caller":"rafthttp/stream.go:294","msg":"stopped TCP streaming connection with remote peer","stream-writer-type":"unknown stream","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.120Z","caller":"rafthttp/pipeline.go:85","msg":"stopped HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.120Z","caller":"rafthttp/stream.go:442","msg":"stopped stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.120Z","caller":"rafthttp/stream.go:442","msg":"stopped stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.120Z","caller":"rafthttp/peer.go:335","msg":"stopped remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:23:13.120Z","caller":"rafthttp/transport.go:355","msg":"removed remote peer","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"45afd95cdd5b378b"}
{"level":"warn","ts":"2023-02-22T08:23:13.127Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"warn","ts":"2023-02-22T08:23:13.136Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"info","ts":"2023-02-22T08:23:13.205Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(5486964048988609832 6189929999477929531)"}
{"level":"warn","ts":"2023-02-22T08:23:13.205Z","caller":"membership/cluster.go:427","msg":"skipped removing already removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"21cea6a99b09da5b"}
{"level":"panic","ts":"2023-02-22T08:23:13.205Z","caller":"rafthttp/transport.go:346","msg":"unexpected removal of unknown remote peer","remote-peer-id":"21cea6a99b09da5b","stacktrace":"go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).removePeer\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:346\ngo.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).RemovePeer\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:329\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyConfChange\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2301\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).apply\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2133\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyEntries\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1357\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyAll\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1179\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).run.func8\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1111\ngo.etcd.io/etcd/pkg/v3/schedule.(*fifo).run\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:157"}
panic: unexpected removal of unknown remote peer

goroutine 225 [running]:
go.uber.org/zap/zapcore.(*CheckedEntry).Write(0xc00b71b800, 0xc0093ab240, 0x1, 0x1)
        /home/remote/sbatsche/.gvm/pkgsets/go1.16.3/global/pkg/mod/go.uber.org/zap@v1.17.0/zapcore/entry.go:234 +0x58d
go.uber.org/zap.(*Logger).Panic(0xc0000bd180, 0x122d9ab, 0x29, 0xc0093ab240, 0x1, 0x1)
        /home/remote/sbatsche/.gvm/pkgsets/go1.16.3/global/pkg/mod/go.uber.org/zap@v1.17.0/logger.go:227 +0x85
go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).removePeer(0xc000563a40, 0x21cea6a99b09da5b)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:346 +0x58c
go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).RemovePeer(0xc000563a40, 0x21cea6a99b09da5b)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:329 +0x7d
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyConfChange(0xc000142a00, 0x1, 0x21cea6a99b09da5b, 0x0, 0x0, 0x0, 0x1d28867813ec3c0e, 0xc00017c480, 0x0, 0x0, ...)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2301 +0x872
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).apply(0xc000142a00, 0xc0086b1af0, 0x1ff, 0x2c5, 0xc00017c480, 0xc009d904d8, 0xc009d90490, 0xc705fd)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2133 +0x59a
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyEntries(0xc000142a00, 0xc00017c480, 0xc003354000)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1357 +0xe5
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyAll(0xc000142a00, 0xc00017c480, 0xc003354000)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1179 +0x88
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).run.func8(0x1399c10, 0xc0008da3c0)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1111 +0x3c
go.etcd.io/etcd/pkg/v3/schedule.(*fifo).run(0xc0006b99e0)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:157 +0xf3
created by go.etcd.io/etcd/pkg/v3/schedule.NewFIFOScheduler
        /tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:70 +0x13b
{"level":"warn","ts":1677054253.9927883,"caller":"flags/flag.go:93","msg":"unrecognized environment variable","environment-variable":"ETCD_UNSUPPORTED_ARCH=x86_64"}
{"level":"info","ts":"2023-02-22T08:24:13.992Z","caller":"etcdmain/etcd.go:72","msg":"Running: ","args":["/usr/local/bin/etcd","--name=etcd-ks-9047366","--listen-client-urls=https://172.27.116.56:2379","--initial-advertise-peer-urls=https://172.27.116.56:2380","--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380","--client-cert-auth=true","--data-dir=/var/lib/rancher/etcd/","--peer-trusted-ca-file=/etc/kubernetes/ssl/kube-ca.pem","--key-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem","--peer-cert-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem","--peer-key-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem","--election-timeout=5000","--heartbeat-interval=500","--initial-cluster-token=etcd-cluster-1","--trusted-ca-file=/etc/kubernetes/ssl/kube-ca.pem","--advertise-client-urls=https://172.27.116.56:2379","--cipher-suites=TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384","--peer-client-cert-auth=true","--listen-peer-urls=https://172.27.116.56:2380","--cert-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem","--initial-cluster-state=new"]}
{"level":"info","ts":"2023-02-22T08:24:13.993Z","caller":"etcdmain/etcd.go:115","msg":"server has been already initialized","data-dir":"/var/lib/rancher/etcd/","dir-type":"member"}
{"level":"info","ts":"2023-02-22T08:24:13.993Z","caller":"embed/etcd.go:131","msg":"configuring peer listeners","listen-peer-urls":["https://172.27.116.56:2380"]}
{"level":"info","ts":"2023-02-22T08:24:13.993Z","caller":"embed/etcd.go:478","msg":"starting with peer TLS","tls-info":"cert = /etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem, key = /etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem, client-cert=, client-key=, trusted-ca = /etc/kubernetes/ssl/kube-ca.pem, client-cert-auth = true, crl-file = ","cipher-suites":["TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256","TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384"]}
{"level":"info","ts":"2023-02-22T08:24:13.993Z","caller":"embed/etcd.go:139","msg":"configuring client listeners","listen-client-urls":["https://172.27.116.56:2379"]}
{"level":"info","ts":"2023-02-22T08:24:13.993Z","caller":"embed/etcd.go:307","msg":"starting an etcd server","etcd-version":"3.5.0","git-sha":"946a5a6f2","go-version":"go1.16.3","go-os":"linux","go-arch":"amd64","max-cpu-set":23,"max-cpu-available":23,"member-initialized":true,"name":"etcd-ks-9047366","data-dir":"/var/lib/rancher/etcd/","wal-dir":"","wal-dir-dedicated":"","member-dir":"/var/lib/rancher/etcd/member","force-new-cluster":false,"heartbeat-interval":"500ms","election-timeout":"5s","initial-election-tick-advance":true,"snapshot-count":100000,"snapshot-catchup-entries":5000,"initial-advertise-peer-urls":["https://172.27.116.56:2380"],"listen-peer-urls":["https://172.27.116.56:2380"],"advertise-client-urls":["https://172.27.116.56:2379"],"listen-client-urls":["https://172.27.116.56:2379"],"listen-metrics-urls":[],"cors":["*"],"host-whitelist":["*"],"initial-cluster":"","initial-cluster-state":"new","initial-cluster-token":"","quota-size-bytes":2147483648,"pre-vote":true,"initial-corrupt-check":false,"corrupt-check-time-interval":"0s","auto-compaction-mode":"periodic","auto-compaction-retention":"0s","auto-compaction-interval":"0s","discovery-url":"","discovery-proxy":"","downgrade-check-interval":"5s"}
{"level":"info","ts":"2023-02-22T08:24:14.035Z","caller":"etcdserver/backend.go:81","msg":"opened backend db","path":"/var/lib/rancher/etcd/member/snap/db","took":"41.444168ms"}
{"level":"info","ts":"2023-02-22T08:24:14.735Z","caller":"etcdserver/server.go:508","msg":"recovered v2 store from snapshot","snapshot-index":4982658,"snapshot-size":"12 kB"}
{"level":"info","ts":"2023-02-22T08:24:14.735Z","caller":"etcdserver/server.go:518","msg":"recovered v3 backend from snapshot","backend-size-bytes":57573376,"backend-size":"58 MB","backend-size-in-use-bytes":44036096,"backend-size-in-use":"44 MB"}
{"level":"info","ts":"2023-02-22T08:24:15.192Z","caller":"etcdserver/raft.go:483","msg":"restarting local member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","commit-index":5037561}
{"level":"info","ts":"2023-02-22T08:24:15.194Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:24:15.194Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b became follower at term 17"}
{"level":"info","ts":"2023-02-22T08:24:15.194Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"newRaft 55e70c89f36a763b [peers: [21cea6a99b09da5b,4c259cbb3b4e1d28,55e70c89f36a763b], term: 17, commit: 5037561, applied: 4982658, lastindex: 5037564, lastterm: 17]"}
{"level":"info","ts":"2023-02-22T08:24:15.195Z","caller":"api/capability.go:75","msg":"enabled capabilities for version","cluster-version":"3.5"}
{"level":"info","ts":"2023-02-22T08:24:15.195Z","caller":"membership/cluster.go:276","msg":"recovered/added member from store","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","recovered-remote-peer-id":"4c259cbb3b4e1d28","recovered-remote-peer-urls":["https://172.27.116.55:2380"]}
{"level":"info","ts":"2023-02-22T08:24:15.195Z","caller":"membership/cluster.go:276","msg":"recovered/added member from store","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","recovered-remote-peer-id":"55e70c89f36a763b","recovered-remote-peer-urls":["https://172.27.116.56:2380"]}
{"level":"info","ts":"2023-02-22T08:24:15.195Z","caller":"membership/cluster.go:285","msg":"set cluster version from store","cluster-version":"3.5"}
{"level":"warn","ts":"2023-02-22T08:24:15.215Z","caller":"auth/store.go:1220","msg":"simple token is not cryptographically signed"}
{"level":"info","ts":"2023-02-22T08:24:15.223Z","caller":"mvcc/kvstore.go:345","msg":"restored last compact revision","meta-bucket-name":"meta","meta-bucket-name-key":"finishedCompactRev","restored-compact-revision":4603957}
{"level":"info","ts":"2023-02-22T08:24:15.293Z","caller":"mvcc/kvstore.go:415","msg":"kvstore restored","current-rev":4606139}
{"level":"info","ts":"2023-02-22T08:24:15.300Z","caller":"etcdserver/quota.go:94","msg":"enabled backend quota with default value","quota-name":"v3-applier","quota-size-bytes":2147483648,"quota-size":"2.1 GB"}
{"level":"info","ts":"2023-02-22T08:24:15.309Z","caller":"rafthttp/peer.go:133","msg":"starting remote peer","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:24:15.309Z","caller":"rafthttp/pipeline.go:72","msg":"started HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:24:15.310Z","caller":"rafthttp/peer.go:137","msg":"started remote peer","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:24:15.310Z","caller":"rafthttp/transport.go:317","msg":"added remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28","remote-peer-urls":["https://172.27.116.55:2380"]}
{"level":"info","ts":"2023-02-22T08:24:15.310Z","caller":"etcdserver/server.go:834","msg":"starting etcd server","local-member-id":"55e70c89f36a763b","local-server-version":"3.5.0","cluster-id":"bb159e7ec69bb5bc","cluster-version":"3.5"}
{"level":"info","ts":"2023-02-22T08:24:15.311Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:24:15.311Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:24:15.311Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:24:15.311Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:24:15.311Z","caller":"etcdserver/server.go:744","msg":"starting initial election tick advance","election-ticks":10}
{"level":"info","ts":"2023-02-22T08:24:15.314Z","caller":"embed/etcd.go:687","msg":"starting with client TLS","tls-info":"cert = /etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem, key = /etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem, client-cert=, client-key=, trusted-ca = /etc/kubernetes/ssl/kube-ca.pem, client-cert-auth = true, crl-file = ","cipher-suites":["TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256","TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384"]}
{"level":"info","ts":"2023-02-22T08:24:15.314Z","caller":"embed/etcd.go:276","msg":"now serving peer/client/metrics","local-member-id":"55e70c89f36a763b","initial-advertise-peer-urls":["https://172.27.116.56:2380"],"listen-peer-urls":["https://172.27.116.56:2380"],"advertise-client-urls":["https://172.27.116.56:2379"],"listen-client-urls":["https://172.27.116.56:2379"],"listen-metrics-urls":[]}
{"level":"info","ts":"2023-02-22T08:24:15.314Z","caller":"embed/etcd.go:580","msg":"serving peer traffic","address":"172.27.116.56:2380"}
{"level":"info","ts":"2023-02-22T08:24:15.314Z","caller":"embed/etcd.go:552","msg":"cmux::serve","address":"172.27.116.56:2380"}
{"level":"info","ts":"2023-02-22T08:24:15.400Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5021471102415353739 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:24:15.401Z","caller":"membership/cluster.go:393","msg":"added member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","added-peer-id":"45afd95cdd5b378b","added-peer-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:24:15.401Z","caller":"rafthttp/peer.go:133","msg":"starting remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.401Z","caller":"rafthttp/pipeline.go:72","msg":"started HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.402Z","caller":"rafthttp/peer.go:137","msg":"started remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.402Z","caller":"rafthttp/transport.go:317","msg":"added remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b","remote-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:24:15.402Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.402Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.402Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.402Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"warn","ts":"2023-02-22T08:24:15.406Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"warn","ts":"2023-02-22T08:24:15.409Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"info","ts":"2023-02-22T08:24:15.517Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:24:15.517Z","caller":"membership/cluster.go:419","msg":"removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"45afd95cdd5b378b","removed-remote-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:24:15.517Z","caller":"rafthttp/peer.go:330","msg":"stopping remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.517Z","caller":"rafthttp/stream.go:294","msg":"stopped TCP streaming connection with remote peer","stream-writer-type":"unknown stream","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.517Z","caller":"rafthttp/stream.go:294","msg":"stopped TCP streaming connection with remote peer","stream-writer-type":"unknown stream","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.517Z","caller":"rafthttp/pipeline.go:85","msg":"stopped HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.517Z","caller":"rafthttp/stream.go:442","msg":"stopped stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.517Z","caller":"rafthttp/stream.go:442","msg":"stopped stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.517Z","caller":"rafthttp/peer.go:335","msg":"stopped remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:24:15.517Z","caller":"rafthttp/transport.go:355","msg":"removed remote peer","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"45afd95cdd5b378b"}
{"level":"warn","ts":"2023-02-22T08:24:15.525Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"warn","ts":"2023-02-22T08:24:15.530Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"info","ts":"2023-02-22T08:24:15.605Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(5486964048988609832 6189929999477929531)"}
{"level":"warn","ts":"2023-02-22T08:24:15.605Z","caller":"membership/cluster.go:427","msg":"skipped removing already removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"21cea6a99b09da5b"}
{"level":"panic","ts":"2023-02-22T08:24:15.605Z","caller":"rafthttp/transport.go:346","msg":"unexpected removal of unknown remote peer","remote-peer-id":"21cea6a99b09da5b","stacktrace":"go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).removePeer\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:346\ngo.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).RemovePeer\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:329\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyConfChange\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2301\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).apply\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2133\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyEntries\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1357\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyAll\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1179\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).run.func8\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1111\ngo.etcd.io/etcd/pkg/v3/schedule.(*fifo).run\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:157"}
panic: unexpected removal of unknown remote peer

goroutine 209 [running]:
go.uber.org/zap/zapcore.(*CheckedEntry).Write(0xc00804e300, 0xc0080524c0, 0x1, 0x1)
        /home/remote/sbatsche/.gvm/pkgsets/go1.16.3/global/pkg/mod/go.uber.org/zap@v1.17.0/zapcore/entry.go:234 +0x58d
go.uber.org/zap.(*Logger).Panic(0xc00067d9a0, 0x122d9ab, 0x29, 0xc0080524c0, 0x1, 0x1)
        /home/remote/sbatsche/.gvm/pkgsets/go1.16.3/global/pkg/mod/go.uber.org/zap@v1.17.0/logger.go:227 +0x85
go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).removePeer(0xc00046ae00, 0x21cea6a99b09da5b)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:346 +0x58c
go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).RemovePeer(0xc00046ae00, 0x21cea6a99b09da5b)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:329 +0x7d
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyConfChange(0xc000143800, 0x1, 0x21cea6a99b09da5b, 0x0, 0x0, 0x0, 0x1d28867813ec3c0e, 0xc0033aa000, 0x0, 0x0, ...)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2301 +0x872
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).apply(0xc000143800, 0xc007d1daf0, 0x1ff, 0x2c5, 0xc0033aa000, 0xc0033a0838, 0xc0033a07f0, 0xc705fd)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2133 +0x59a
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyEntries(0xc000143800, 0xc0033aa000, 0xc0042e5c30)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1357 +0xe5
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyAll(0xc000143800, 0xc0033aa000, 0xc0042e5c30)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1179 +0x88
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).run.func8(0x1399c10, 0xc0033a2040)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1111 +0x3c
go.etcd.io/etcd/pkg/v3/schedule.(*fifo).run(0xc000654060)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:157 +0xf3
created by go.etcd.io/etcd/pkg/v3/schedule.NewFIFOScheduler
        /tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:70 +0x13b
{"level":"warn","ts":1677054316.273973,"caller":"flags/flag.go:93","msg":"unrecognized environment variable","environment-variable":"ETCD_UNSUPPORTED_ARCH=x86_64"}
{"level":"info","ts":"2023-02-22T08:25:16.274Z","caller":"etcdmain/etcd.go:72","msg":"Running: ","args":["/usr/local/bin/etcd","--name=etcd-ks-9047366","--listen-client-urls=https://172.27.116.56:2379","--initial-advertise-peer-urls=https://172.27.116.56:2380","--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380","--client-cert-auth=true","--data-dir=/var/lib/rancher/etcd/","--peer-trusted-ca-file=/etc/kubernetes/ssl/kube-ca.pem","--key-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem","--peer-cert-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem","--peer-key-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem","--election-timeout=5000","--heartbeat-interval=500","--initial-cluster-token=etcd-cluster-1","--trusted-ca-file=/etc/kubernetes/ssl/kube-ca.pem","--advertise-client-urls=https://172.27.116.56:2379","--cipher-suites=TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384","--peer-client-cert-auth=true","--listen-peer-urls=https://172.27.116.56:2380","--cert-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem","--initial-cluster-state=new"]}
{"level":"info","ts":"2023-02-22T08:25:16.274Z","caller":"etcdmain/etcd.go:115","msg":"server has been already initialized","data-dir":"/var/lib/rancher/etcd/","dir-type":"member"}
{"level":"info","ts":"2023-02-22T08:25:16.274Z","caller":"embed/etcd.go:131","msg":"configuring peer listeners","listen-peer-urls":["https://172.27.116.56:2380"]}
{"level":"info","ts":"2023-02-22T08:25:16.274Z","caller":"embed/etcd.go:478","msg":"starting with peer TLS","tls-info":"cert = /etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem, key = /etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem, client-cert=, client-key=, trusted-ca = /etc/kubernetes/ssl/kube-ca.pem, client-cert-auth = true, crl-file = ","cipher-suites":["TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256","TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384"]}
{"level":"info","ts":"2023-02-22T08:25:16.274Z","caller":"embed/etcd.go:139","msg":"configuring client listeners","listen-client-urls":["https://172.27.116.56:2379"]}
{"level":"info","ts":"2023-02-22T08:25:16.275Z","caller":"embed/etcd.go:307","msg":"starting an etcd server","etcd-version":"3.5.0","git-sha":"946a5a6f2","go-version":"go1.16.3","go-os":"linux","go-arch":"amd64","max-cpu-set":23,"max-cpu-available":23,"member-initialized":true,"name":"etcd-ks-9047366","data-dir":"/var/lib/rancher/etcd/","wal-dir":"","wal-dir-dedicated":"","member-dir":"/var/lib/rancher/etcd/member","force-new-cluster":false,"heartbeat-interval":"500ms","election-timeout":"5s","initial-election-tick-advance":true,"snapshot-count":100000,"snapshot-catchup-entries":5000,"initial-advertise-peer-urls":["https://172.27.116.56:2380"],"listen-peer-urls":["https://172.27.116.56:2380"],"advertise-client-urls":["https://172.27.116.56:2379"],"listen-client-urls":["https://172.27.116.56:2379"],"listen-metrics-urls":[],"cors":["*"],"host-whitelist":["*"],"initial-cluster":"","initial-cluster-state":"new","initial-cluster-token":"","quota-size-bytes":2147483648,"pre-vote":true,"initial-corrupt-check":false,"corrupt-check-time-interval":"0s","auto-compaction-mode":"periodic","auto-compaction-retention":"0s","auto-compaction-interval":"0s","discovery-url":"","discovery-proxy":"","downgrade-check-interval":"5s"}
{"level":"info","ts":"2023-02-22T08:25:16.318Z","caller":"etcdserver/backend.go:81","msg":"opened backend db","path":"/var/lib/rancher/etcd/member/snap/db","took":"42.474883ms"}
{"level":"info","ts":"2023-02-22T08:25:17.035Z","caller":"etcdserver/server.go:508","msg":"recovered v2 store from snapshot","snapshot-index":4982658,"snapshot-size":"12 kB"}
{"level":"info","ts":"2023-02-22T08:25:17.035Z","caller":"etcdserver/server.go:518","msg":"recovered v3 backend from snapshot","backend-size-bytes":57573376,"backend-size":"58 MB","backend-size-in-use-bytes":44036096,"backend-size-in-use":"44 MB"}
{"level":"info","ts":"2023-02-22T08:25:17.515Z","caller":"etcdserver/raft.go:483","msg":"restarting local member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","commit-index":5037561}
{"level":"info","ts":"2023-02-22T08:25:17.518Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:25:17.518Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b became follower at term 17"}
{"level":"info","ts":"2023-02-22T08:25:17.518Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"newRaft 55e70c89f36a763b [peers: [21cea6a99b09da5b,4c259cbb3b4e1d28,55e70c89f36a763b], term: 17, commit: 5037561, applied: 4982658, lastindex: 5037564, lastterm: 17]"}
{"level":"info","ts":"2023-02-22T08:25:17.518Z","caller":"api/capability.go:75","msg":"enabled capabilities for version","cluster-version":"3.5"}
{"level":"info","ts":"2023-02-22T08:25:17.518Z","caller":"membership/cluster.go:276","msg":"recovered/added member from store","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","recovered-remote-peer-id":"4c259cbb3b4e1d28","recovered-remote-peer-urls":["https://172.27.116.55:2380"]}
{"level":"info","ts":"2023-02-22T08:25:17.518Z","caller":"membership/cluster.go:276","msg":"recovered/added member from store","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","recovered-remote-peer-id":"55e70c89f36a763b","recovered-remote-peer-urls":["https://172.27.116.56:2380"]}
{"level":"info","ts":"2023-02-22T08:25:17.518Z","caller":"membership/cluster.go:285","msg":"set cluster version from store","cluster-version":"3.5"}
{"level":"warn","ts":"2023-02-22T08:25:17.557Z","caller":"auth/store.go:1220","msg":"simple token is not cryptographically signed"}
{"level":"info","ts":"2023-02-22T08:25:17.593Z","caller":"mvcc/kvstore.go:345","msg":"restored last compact revision","meta-bucket-name":"meta","meta-bucket-name-key":"finishedCompactRev","restored-compact-revision":4603957}
{"level":"info","ts":"2023-02-22T08:25:17.664Z","caller":"mvcc/kvstore.go:415","msg":"kvstore restored","current-rev":4606139}
{"level":"info","ts":"2023-02-22T08:25:17.693Z","caller":"etcdserver/quota.go:94","msg":"enabled backend quota with default value","quota-name":"v3-applier","quota-size-bytes":2147483648,"quota-size":"2.1 GB"}
{"level":"info","ts":"2023-02-22T08:25:17.768Z","caller":"rafthttp/peer.go:133","msg":"starting remote peer","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:25:17.768Z","caller":"rafthttp/pipeline.go:72","msg":"started HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:25:17.769Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:25:17.769Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:25:17.770Z","caller":"rafthttp/peer.go:137","msg":"started remote peer","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:25:17.770Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:25:17.770Z","caller":"rafthttp/transport.go:317","msg":"added remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28","remote-peer-urls":["https://172.27.116.55:2380"]}
{"level":"info","ts":"2023-02-22T08:25:17.770Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:25:17.770Z","caller":"etcdserver/server.go:834","msg":"starting etcd server","local-member-id":"55e70c89f36a763b","local-server-version":"3.5.0","cluster-id":"bb159e7ec69bb5bc","cluster-version":"3.5"}
{"level":"info","ts":"2023-02-22T08:25:17.770Z","caller":"etcdserver/server.go:744","msg":"starting initial election tick advance","election-ticks":10}
{"level":"info","ts":"2023-02-22T08:25:17.773Z","caller":"embed/etcd.go:687","msg":"starting with client TLS","tls-info":"cert = /etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem, key = /etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem, client-cert=, client-key=, trusted-ca = /etc/kubernetes/ssl/kube-ca.pem, client-cert-auth = true, crl-file = ","cipher-suites":["TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256","TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384"]}
{"level":"info","ts":"2023-02-22T08:25:17.773Z","caller":"embed/etcd.go:276","msg":"now serving peer/client/metrics","local-member-id":"55e70c89f36a763b","initial-advertise-peer-urls":["https://172.27.116.56:2380"],"listen-peer-urls":["https://172.27.116.56:2380"],"advertise-client-urls":["https://172.27.116.56:2379"],"listen-client-urls":["https://172.27.116.56:2379"],"listen-metrics-urls":[]}
{"level":"info","ts":"2023-02-22T08:25:17.773Z","caller":"embed/etcd.go:580","msg":"serving peer traffic","address":"172.27.116.56:2380"}
{"level":"info","ts":"2023-02-22T08:25:17.773Z","caller":"embed/etcd.go:552","msg":"cmux::serve","address":"172.27.116.56:2380"}
{"level":"info","ts":"2023-02-22T08:25:17.856Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5021471102415353739 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:25:17.856Z","caller":"membership/cluster.go:393","msg":"added member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","added-peer-id":"45afd95cdd5b378b","added-peer-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:25:17.856Z","caller":"rafthttp/peer.go:133","msg":"starting remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.857Z","caller":"rafthttp/pipeline.go:72","msg":"started HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.857Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.857Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.857Z","caller":"rafthttp/peer.go:137","msg":"started remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.857Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.857Z","caller":"rafthttp/transport.go:317","msg":"added remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b","remote-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:25:17.857Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"warn","ts":"2023-02-22T08:25:17.862Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"warn","ts":"2023-02-22T08:25:17.866Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"info","ts":"2023-02-22T08:25:17.984Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:25:17.984Z","caller":"membership/cluster.go:419","msg":"removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"45afd95cdd5b378b","removed-remote-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:25:17.984Z","caller":"rafthttp/peer.go:330","msg":"stopping remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.984Z","caller":"rafthttp/stream.go:294","msg":"stopped TCP streaming connection with remote peer","stream-writer-type":"unknown stream","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.984Z","caller":"rafthttp/stream.go:294","msg":"stopped TCP streaming connection with remote peer","stream-writer-type":"unknown stream","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.984Z","caller":"rafthttp/pipeline.go:85","msg":"stopped HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.985Z","caller":"rafthttp/stream.go:442","msg":"stopped stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.985Z","caller":"rafthttp/stream.go:442","msg":"stopped stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.985Z","caller":"rafthttp/peer.go:335","msg":"stopped remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:25:17.985Z","caller":"rafthttp/transport.go:355","msg":"removed remote peer","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"45afd95cdd5b378b"}
{"level":"warn","ts":"2023-02-22T08:25:17.992Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"warn","ts":"2023-02-22T08:25:17.997Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"info","ts":"2023-02-22T08:25:18.060Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(5486964048988609832 6189929999477929531)"}
{"level":"warn","ts":"2023-02-22T08:25:18.060Z","caller":"membership/cluster.go:427","msg":"skipped removing already removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"21cea6a99b09da5b"}
{"level":"panic","ts":"2023-02-22T08:25:18.060Z","caller":"rafthttp/transport.go:346","msg":"unexpected removal of unknown remote peer","remote-peer-id":"21cea6a99b09da5b","stacktrace":"go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).removePeer\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:346\ngo.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).RemovePeer\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:329\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyConfChange\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2301\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).apply\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2133\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyEntries\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1357\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyAll\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1179\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).run.func8\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1111\ngo.etcd.io/etcd/pkg/v3/schedule.(*fifo).run\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:157"}
panic: unexpected removal of unknown remote peer

goroutine 203 [running]:
go.uber.org/zap/zapcore.(*CheckedEntry).Write(0xc005bfe000, 0xc00c09ef00, 0x1, 0x1)
        /home/remote/sbatsche/.gvm/pkgsets/go1.16.3/global/pkg/mod/go.uber.org/zap@v1.17.0/zapcore/entry.go:234 +0x58d
go.uber.org/zap.(*Logger).Panic(0xc0000bdf90, 0x122d9ab, 0x29, 0xc00c09ef00, 0x1, 0x1)
        /home/remote/sbatsche/.gvm/pkgsets/go1.16.3/global/pkg/mod/go.uber.org/zap@v1.17.0/logger.go:227 +0x85
go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).removePeer(0xc000564c40, 0x21cea6a99b09da5b)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:346 +0x58c
go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).RemovePeer(0xc000564c40, 0x21cea6a99b09da5b)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:329 +0x7d
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyConfChange(0xc00052c700, 0x1, 0x21cea6a99b09da5b, 0x0, 0x0, 0x0, 0x1d28867813ec3c0e, 0xc0001fa300, 0x0, 0x0, ...)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2301 +0x872
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).apply(0xc00052c700, 0xc007c9daf0, 0x1ff, 0x2c5, 0xc0001fa300, 0xc003a73af8, 0xc003a73ab0, 0xc705fd)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2133 +0x59a
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyEntries(0xc00052c700, 0xc0001fa300, 0xc00a0a9290)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1357 +0xe5
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyAll(0xc00052c700, 0xc0001fa300, 0xc00a0a9290)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1179 +0x88
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).run.func8(0x1399c10, 0xc0000e85c0)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1111 +0x3c
go.etcd.io/etcd/pkg/v3/schedule.(*fifo).run(0xc000359200)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:157 +0xf3
created by go.etcd.io/etcd/pkg/v3/schedule.NewFIFOScheduler
        /tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:70 +0x13b
{"level":"warn","ts":1677054379.5310004,"caller":"flags/flag.go:93","msg":"unrecognized environment variable","environment-variable":"ETCD_UNSUPPORTED_ARCH=x86_64"}
{"level":"info","ts":"2023-02-22T08:26:19.531Z","caller":"etcdmain/etcd.go:72","msg":"Running: ","args":["/usr/local/bin/etcd","--name=etcd-ks-9047366","--listen-client-urls=https://172.27.116.56:2379","--initial-advertise-peer-urls=https://172.27.116.56:2380","--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380","--client-cert-auth=true","--data-dir=/var/lib/rancher/etcd/","--peer-trusted-ca-file=/etc/kubernetes/ssl/kube-ca.pem","--key-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem","--peer-cert-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem","--peer-key-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem","--election-timeout=5000","--heartbeat-interval=500","--initial-cluster-token=etcd-cluster-1","--trusted-ca-file=/etc/kubernetes/ssl/kube-ca.pem","--advertise-client-urls=https://172.27.116.56:2379","--cipher-suites=TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384","--peer-client-cert-auth=true","--listen-peer-urls=https://172.27.116.56:2380","--cert-file=/etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem","--initial-cluster-state=new"]}
{"level":"info","ts":"2023-02-22T08:26:19.531Z","caller":"etcdmain/etcd.go:115","msg":"server has been already initialized","data-dir":"/var/lib/rancher/etcd/","dir-type":"member"}
{"level":"info","ts":"2023-02-22T08:26:19.531Z","caller":"embed/etcd.go:131","msg":"configuring peer listeners","listen-peer-urls":["https://172.27.116.56:2380"]}
{"level":"info","ts":"2023-02-22T08:26:19.531Z","caller":"embed/etcd.go:478","msg":"starting with peer TLS","tls-info":"cert = /etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem, key = /etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem, client-cert=, client-key=, trusted-ca = /etc/kubernetes/ssl/kube-ca.pem, client-cert-auth = true, crl-file = ","cipher-suites":["TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256","TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384"]}
{"level":"info","ts":"2023-02-22T08:26:19.533Z","caller":"embed/etcd.go:139","msg":"configuring client listeners","listen-client-urls":["https://172.27.116.56:2379"]}
{"level":"info","ts":"2023-02-22T08:26:19.533Z","caller":"embed/etcd.go:307","msg":"starting an etcd server","etcd-version":"3.5.0","git-sha":"946a5a6f2","go-version":"go1.16.3","go-os":"linux","go-arch":"amd64","max-cpu-set":23,"max-cpu-available":23,"member-initialized":true,"name":"etcd-ks-9047366","data-dir":"/var/lib/rancher/etcd/","wal-dir":"","wal-dir-dedicated":"","member-dir":"/var/lib/rancher/etcd/member","force-new-cluster":false,"heartbeat-interval":"500ms","election-timeout":"5s","initial-election-tick-advance":true,"snapshot-count":100000,"snapshot-catchup-entries":5000,"initial-advertise-peer-urls":["https://172.27.116.56:2380"],"listen-peer-urls":["https://172.27.116.56:2380"],"advertise-client-urls":["https://172.27.116.56:2379"],"listen-client-urls":["https://172.27.116.56:2379"],"listen-metrics-urls":[],"cors":["*"],"host-whitelist":["*"],"initial-cluster":"","initial-cluster-state":"new","initial-cluster-token":"","quota-size-bytes":2147483648,"pre-vote":true,"initial-corrupt-check":false,"corrupt-check-time-interval":"0s","auto-compaction-mode":"periodic","auto-compaction-retention":"0s","auto-compaction-interval":"0s","discovery-url":"","discovery-proxy":"","downgrade-check-interval":"5s"}
{"level":"info","ts":"2023-02-22T08:26:19.576Z","caller":"etcdserver/backend.go:81","msg":"opened backend db","path":"/var/lib/rancher/etcd/member/snap/db","took":"43.031661ms"}
{"level":"info","ts":"2023-02-22T08:26:20.327Z","caller":"etcdserver/server.go:508","msg":"recovered v2 store from snapshot","snapshot-index":4982658,"snapshot-size":"12 kB"}
{"level":"info","ts":"2023-02-22T08:26:20.327Z","caller":"etcdserver/server.go:518","msg":"recovered v3 backend from snapshot","backend-size-bytes":57573376,"backend-size":"58 MB","backend-size-in-use-bytes":44036096,"backend-size-in-use":"44 MB"}
{"level":"info","ts":"2023-02-22T08:26:20.801Z","caller":"etcdserver/raft.go:483","msg":"restarting local member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","commit-index":5037561}
{"level":"info","ts":"2023-02-22T08:26:20.804Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:26:20.804Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b became follower at term 17"}
{"level":"info","ts":"2023-02-22T08:26:20.804Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"newRaft 55e70c89f36a763b [peers: [21cea6a99b09da5b,4c259cbb3b4e1d28,55e70c89f36a763b], term: 17, commit: 5037561, applied: 4982658, lastindex: 5037564, lastterm: 17]"}
{"level":"info","ts":"2023-02-22T08:26:20.804Z","caller":"api/capability.go:75","msg":"enabled capabilities for version","cluster-version":"3.5"}
{"level":"info","ts":"2023-02-22T08:26:20.804Z","caller":"membership/cluster.go:276","msg":"recovered/added member from store","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","recovered-remote-peer-id":"4c259cbb3b4e1d28","recovered-remote-peer-urls":["https://172.27.116.55:2380"]}
{"level":"info","ts":"2023-02-22T08:26:20.804Z","caller":"membership/cluster.go:276","msg":"recovered/added member from store","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","recovered-remote-peer-id":"55e70c89f36a763b","recovered-remote-peer-urls":["https://172.27.116.56:2380"]}
{"level":"info","ts":"2023-02-22T08:26:20.804Z","caller":"membership/cluster.go:285","msg":"set cluster version from store","cluster-version":"3.5"}
{"level":"warn","ts":"2023-02-22T08:26:20.818Z","caller":"auth/store.go:1220","msg":"simple token is not cryptographically signed"}
{"level":"info","ts":"2023-02-22T08:26:20.826Z","caller":"mvcc/kvstore.go:345","msg":"restored last compact revision","meta-bucket-name":"meta","meta-bucket-name-key":"finishedCompactRev","restored-compact-revision":4603957}
{"level":"info","ts":"2023-02-22T08:26:20.900Z","caller":"mvcc/kvstore.go:415","msg":"kvstore restored","current-rev":4606139}
{"level":"info","ts":"2023-02-22T08:26:20.967Z","caller":"etcdserver/quota.go:94","msg":"enabled backend quota with default value","quota-name":"v3-applier","quota-size-bytes":2147483648,"quota-size":"2.1 GB"}
{"level":"info","ts":"2023-02-22T08:26:20.984Z","caller":"rafthttp/peer.go:133","msg":"starting remote peer","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:26:20.984Z","caller":"rafthttp/pipeline.go:72","msg":"started HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:26:20.985Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:26:20.985Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:26:20.986Z","caller":"rafthttp/peer.go:137","msg":"started remote peer","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:26:20.986Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:26:20.986Z","caller":"rafthttp/transport.go:317","msg":"added remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28","remote-peer-urls":["https://172.27.116.55:2380"]}
{"level":"info","ts":"2023-02-22T08:26:20.986Z","caller":"etcdserver/server.go:834","msg":"starting etcd server","local-member-id":"55e70c89f36a763b","local-server-version":"3.5.0","cluster-id":"bb159e7ec69bb5bc","cluster-version":"3.5"}
{"level":"info","ts":"2023-02-22T08:26:20.986Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"4c259cbb3b4e1d28"}
{"level":"info","ts":"2023-02-22T08:26:20.986Z","caller":"etcdserver/server.go:744","msg":"starting initial election tick advance","election-ticks":10}
{"level":"info","ts":"2023-02-22T08:26:20.990Z","caller":"embed/etcd.go:687","msg":"starting with client TLS","tls-info":"cert = /etc/kubernetes/ssl/kube-etcd-172-27-116-56.pem, key = /etc/kubernetes/ssl/kube-etcd-172-27-116-56-key.pem, client-cert=, client-key=, trusted-ca = /etc/kubernetes/ssl/kube-ca.pem, client-cert-auth = true, crl-file = ","cipher-suites":["TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256","TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384"]}
{"level":"info","ts":"2023-02-22T08:26:20.990Z","caller":"embed/etcd.go:580","msg":"serving peer traffic","address":"172.27.116.56:2380"}
{"level":"info","ts":"2023-02-22T08:26:20.990Z","caller":"embed/etcd.go:552","msg":"cmux::serve","address":"172.27.116.56:2380"}
{"level":"info","ts":"2023-02-22T08:26:20.990Z","caller":"embed/etcd.go:276","msg":"now serving peer/client/metrics","local-member-id":"55e70c89f36a763b","initial-advertise-peer-urls":["https://172.27.116.56:2380"],"listen-peer-urls":["https://172.27.116.56:2380"],"advertise-client-urls":["https://172.27.116.56:2379"],"listen-client-urls":["https://172.27.116.56:2379"],"listen-metrics-urls":[]}
{"level":"info","ts":"2023-02-22T08:26:21.076Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5021471102415353739 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:26:21.076Z","caller":"membership/cluster.go:393","msg":"added member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","added-peer-id":"45afd95cdd5b378b","added-peer-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:26:21.076Z","caller":"rafthttp/peer.go:133","msg":"starting remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.076Z","caller":"rafthttp/pipeline.go:72","msg":"started HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.077Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.077Z","caller":"rafthttp/peer.go:137","msg":"started remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.077Z","caller":"rafthttp/transport.go:317","msg":"added remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b","remote-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:26:21.077Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.077Z","caller":"rafthttp/stream.go:395","msg":"started stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.077Z","caller":"rafthttp/stream.go:169","msg":"started stream writer with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"warn","ts":"2023-02-22T08:26:21.083Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"warn","ts":"2023-02-22T08:26:21.085Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"info","ts":"2023-02-22T08:26:21.204Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(2436067695834815067 5486964048988609832 6189929999477929531)"}
{"level":"info","ts":"2023-02-22T08:26:21.204Z","caller":"membership/cluster.go:419","msg":"removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"45afd95cdd5b378b","removed-remote-peer-urls":["https://172.27.116.58:2380"]}
{"level":"info","ts":"2023-02-22T08:26:21.204Z","caller":"rafthttp/peer.go:330","msg":"stopping remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.204Z","caller":"rafthttp/stream.go:294","msg":"stopped TCP streaming connection with remote peer","stream-writer-type":"unknown stream","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.204Z","caller":"rafthttp/stream.go:294","msg":"stopped TCP streaming connection with remote peer","stream-writer-type":"unknown stream","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.204Z","caller":"rafthttp/pipeline.go:85","msg":"stopped HTTP pipelining with remote peer","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.204Z","caller":"rafthttp/stream.go:442","msg":"stopped stream reader with remote peer","stream-reader-type":"stream MsgApp v2","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.204Z","caller":"rafthttp/stream.go:442","msg":"stopped stream reader with remote peer","stream-reader-type":"stream Message","local-member-id":"55e70c89f36a763b","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.204Z","caller":"rafthttp/peer.go:335","msg":"stopped remote peer","remote-peer-id":"45afd95cdd5b378b"}
{"level":"info","ts":"2023-02-22T08:26:21.204Z","caller":"rafthttp/transport.go:355","msg":"removed remote peer","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"45afd95cdd5b378b"}
{"level":"warn","ts":"2023-02-22T08:26:21.212Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"warn","ts":"2023-02-22T08:26:21.217Z","caller":"membership/cluster.go:461","msg":"skipped attributes update of removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","updated-peer-id":"21cea6a99b09da5b"}
{"level":"info","ts":"2023-02-22T08:26:21.282Z","logger":"raft","caller":"etcdserver/zap_raft.go:77","msg":"55e70c89f36a763b switched to configuration voters=(5486964048988609832 6189929999477929531)"}
{"level":"warn","ts":"2023-02-22T08:26:21.282Z","caller":"membership/cluster.go:427","msg":"skipped removing already removed member","cluster-id":"bb159e7ec69bb5bc","local-member-id":"55e70c89f36a763b","removed-remote-peer-id":"21cea6a99b09da5b"}
{"level":"panic","ts":"2023-02-22T08:26:21.282Z","caller":"rafthttp/transport.go:346","msg":"unexpected removal of unknown remote peer","remote-peer-id":"21cea6a99b09da5b","stacktrace":"go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).removePeer\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:346\ngo.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).RemovePeer\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:329\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyConfChange\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2301\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).apply\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2133\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyEntries\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1357\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyAll\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1179\ngo.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).run.func8\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1111\ngo.etcd.io/etcd/pkg/v3/schedule.(*fifo).run\n\t/tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:157"}
panic: unexpected removal of unknown remote peer

goroutine 209 [running]:
go.uber.org/zap/zapcore.(*CheckedEntry).Write(0xc004f41bc0, 0xc00bcd2280, 0x1, 0x1)
        /home/remote/sbatsche/.gvm/pkgsets/go1.16.3/global/pkg/mod/go.uber.org/zap@v1.17.0/zapcore/entry.go:234 +0x58d
go.uber.org/zap.(*Logger).Panic(0xc00068cfa0, 0x122d9ab, 0x29, 0xc00bcd2280, 0x1, 0x1)
        /home/remote/sbatsche/.gvm/pkgsets/go1.16.3/global/pkg/mod/go.uber.org/zap@v1.17.0/logger.go:227 +0x85
go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).removePeer(0xc000700700, 0x21cea6a99b09da5b)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:346 +0x58c
go.etcd.io/etcd/server/v3/etcdserver/api/rafthttp.(*Transport).RemovePeer(0xc000700700, 0x21cea6a99b09da5b)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/api/rafthttp/transport.go:329 +0x7d
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyConfChange(0xc000507100, 0x1, 0x21cea6a99b09da5b, 0x0, 0x0, 0x0, 0x1d28867813ec3c0e, 0xc000138300, 0x0, 0x0, ...)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2301 +0x872
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).apply(0xc000507100, 0xc007f7daf0, 0x1ff, 0x2c5, 0xc000138300, 0xc00232f0d8, 0xc00232f090, 0xc705fd)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:2133 +0x59a
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyEntries(0xc000507100, 0xc000138300, 0xc003e46840)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1357 +0xe5
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).applyAll(0xc000507100, 0xc000138300, 0xc003e46840)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1179 +0x88
go.etcd.io/etcd/server/v3/etcdserver.(*EtcdServer).run.func8(0x1399c10, 0xc009b2c280)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/server/etcdserver/server.go:1111 +0x3c
go.etcd.io/etcd/pkg/v3/schedule.(*fifo).run(0xc0000b2a80)
        /tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:157 +0xf3
created by go.etcd.io/etcd/pkg/v3/schedule.NewFIFOScheduler
        /tmp/etcd-release-3.5.0/etcd/release/etcd/pkg/schedule/schedule.go:70 +0x13b
root@ks-9047366:~#
```  