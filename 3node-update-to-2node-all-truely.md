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
DEBU[0000] Docker Info found for host [172.27.116.66]: types.Info{ID:"7T67:DXEC:PYY6:VISK:5RG4:M2UV:N6NE:MAI4:QNBJ:PXN6:JNZ3:E6XT", Containers:31, ContainersRunning:16, ContainersPaused:0, ContainersStopped:15, Images:43, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:110, OomKillDisable:true, NGoroutines:102, SystemTime:"2023-02-22T18:05:55.063193885+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc000470a80), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047366", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
DEBU[0000] Docker Info found for host [172.27.116.65]: types.Info{ID:"PXEX:4WFR:EIA2:YQWO:7QYJ:AV77:D5FS:5CXU:O7VZ:7V3L:V24Y:IHH2", Containers:87, ContainersRunning:14, ContainersPaused:0, ContainersStopped:73, Images:47, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:99, OomKillDisable:true, NGoroutines:94, SystemTime:"2023-02-22T18:05:54.516780674+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc0001d4230), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047489", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
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
INFO[0000] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0000] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
DEBU[0000] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0000] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
DEBU[0000] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0000] Starting container [cert-deployer] on host [172.27.116.66], try #1
INFO[0001] Starting container [cert-deployer] on host [172.27.116.65], try #1
DEBU[0002] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0002] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
DEBU[0002] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0002] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0007] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
INFO[0007] Removing container [cert-deployer] on host [172.27.116.66], try #1
INFO[0007] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0007] Removing container [cert-deployer] on host [172.27.116.65], try #1
INFO[0008] [reconcile] Rebuilding and updating local kube config
DEBU[0008] [reconcile] Rebuilding and updating local kube config, creating new kubeconfig
DEBU[0008] Deploying admin Kubeconfig locally at [./kube_config_cluster.yml]
INFO[0008] Successfully Deployed local admin kubeconfig at [./kube_config_cluster.yml]
DEBU[0008] [version] Using ./kube_config_cluster.yml to connect to Kubernetes cluster..
DEBU[0008] [version] Getting Kubernetes server version..
INFO[0008] [reconcile] host [172.27.116.65] is a control plane node with reachable Kubernetes API endpoint in the cluster
INFO[0008] [certificates] Successfully deployed kubernetes certificates to Cluster nodes
INFO[0008] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.65]
DEBU[0008] [remove/file-deployer] Checking if container is running on host [172.27.116.65]
DEBU[0008] [remove/file-deployer] Container doesn't exist on host [172.27.116.65]
DEBU[0008] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0008] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0008] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0009] Starting container [file-deployer] on host [172.27.116.65], try #1
INFO[0010] Successfully started [file-deployer] container on host [172.27.116.65]
INFO[0010] Waiting for [file-deployer] container to exit on host [172.27.116.65]
INFO[0010] Waiting for [file-deployer] container to exit on host [172.27.116.65]
DEBU[0011] Exit code for [file-deployer] container on host [172.27.116.65] is [0]
DEBU[0011] [remove/file-deployer] Checking if container is running on host [172.27.116.65]
DEBU[0011] [remove/file-deployer] Removing container on host [172.27.116.65]
INFO[0011] Removing container [file-deployer] on host [172.27.116.65], try #1
INFO[0012] [remove/file-deployer] Successfully removed container on host [172.27.116.65]
DEBU[0012] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.65]
INFO[0012] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.66]
DEBU[0012] [remove/file-deployer] Checking if container is running on host [172.27.116.66]
DEBU[0012] [remove/file-deployer] Container doesn't exist on host [172.27.116.66]
DEBU[0012] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0012] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0012] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0013] Starting container [file-deployer] on host [172.27.116.66], try #1
INFO[0014] Successfully started [file-deployer] container on host [172.27.116.66]
INFO[0014] Waiting for [file-deployer] container to exit on host [172.27.116.66]
INFO[0014] Waiting for [file-deployer] container to exit on host [172.27.116.66]
DEBU[0015] Exit code for [file-deployer] container on host [172.27.116.66] is [0]
DEBU[0015] [remove/file-deployer] Checking if container is running on host [172.27.116.66]
DEBU[0015] [remove/file-deployer] Removing container on host [172.27.116.66]
INFO[0015] Removing container [file-deployer] on host [172.27.116.66], try #1
INFO[0015] [remove/file-deployer] Successfully removed container on host [172.27.116.66]
DEBU[0015] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.66]
INFO[0015] [/etc/kubernetes/audit-policy.yaml] Successfully deployed audit policy file to Cluster control nodes
INFO[0015] [reconcile] Reconciling cluster state
INFO[0015] [reconcile] Check etcd hosts to be deleted
DEBU[0015] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0015] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0015] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0015] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0015] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0015] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0015] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0015] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0015] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0015] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0015] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0015] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0015] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0015] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0015] [remove/etcd] Removing member [etcd-ks-9047368] from etcd cluster
INFO[0016] [remove/etcd] Checking etcd cluster health on [etcd-ks-9047489] after removing [etcd-ks-9047368]
DEBU[0016] [remove/etcd] healthCheckURL for checking etcd cluster health on [etcd-ks-9047489] after removing [ks-9047368]: [https://172.27.116.55:2379/health]
DEBU[0016] [etcd] check etcd cluster health on host [172.27.116.65]
INFO[0016] [etcd] etcd host [172.27.116.65] reported healthy=true
INFO[0016] [remove/etcd] etcd cluster health is healthy on [etcd-ks-9047489] after removing [etcd-ks-9047368]
DEBU[0016] Total time between etcd member deleted and etcd cluster healthy is: [110.982943ms]
INFO[0016] [remove/etcd] Successfully removed member [etcd-ks-9047368] from etcd cluster
INFO[0016] [hosts] host [172.27.116.67] has another role, skipping delete from kubernetes cluster
INFO[0016] [dialer] Setup tunnel for host [172.27.116.67]
DEBU[0016] Connecting to Docker API for host [172.27.116.67]
DEBU[0016] Docker Info found for host [172.27.116.67]: types.Info{ID:"VN5L:TH7K:7SRQ:LLCZ:F7QU:TJUR:7AZ7:ETFA:NIKN:KE4N:OEJE:KWUZ", Containers:40, ContainersRunning:20, ContainersPaused:0, ContainersStopped:20, Images:33, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:128, OomKillDisable:true, NGoroutines:115, SystemTime:"2023-02-22T18:06:10.809698539+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc00024f6c0), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047368", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
INFO[0016] [etcd] Tearing down etcd plane..
DEBU[0016] [remove/etcd] Checking if container is running on host [172.27.116.67]
DEBU[0016] [remove/etcd] Removing container on host [172.27.116.67]
INFO[0016] Removing container [etcd] on host [172.27.116.67], try #1
INFO[0018] [remove/etcd] Successfully removed container on host [172.27.116.67]
DEBU[0018] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.67]
DEBU[0018] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.67]
INFO[0018] Removing container [etcd-rolling-snapshots] on host [172.27.116.67], try #1
INFO[0019] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.67]
INFO[0019] [etcd] Successfully tore down etcd plane..
INFO[0019] [hosts] Host [172.27.116.67] is already a worker or control host, skipping cleanup certs.
INFO[0019] [hosts] Cleaning up host [172.27.116.67]
DEBU[0019] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0019] [hosts] Running cleaner container on host [172.27.116.67]
DEBU[0019] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0019] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0020] Starting container [kube-cleaner] on host [172.27.116.67], try #1
INFO[0022] [kube-cleaner] Successfully started [kube-cleaner] container on host [172.27.116.67]
INFO[0022] Waiting for [kube-cleaner] container to exit on host [172.27.116.67]
DEBU[0023] Exit code for [kube-cleaner] container on host [172.27.116.67] is [0]
INFO[0023] [hosts] Removing cleaner container on host [172.27.116.67]
INFO[0023] Removing container [kube-cleaner] on host [172.27.116.67], try #1
INFO[0023] [hosts] Removing dead container logs on host [172.27.116.67]
DEBU[0023] [cleanup] Starting log link cleanup on host [172.27.116.67]
DEBU[0023] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.67]
DEBU[0023] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.67]
DEBU[0023] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0023] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0024] Starting container [rke-log-cleaner] on host [172.27.116.67], try #1
INFO[0025] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.67]
DEBU[0025] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.67]
DEBU[0026] [remove/rke-log-cleaner] Removing container on host [172.27.116.67]
INFO[0026] Removing container [rke-log-cleaner] on host [172.27.116.67], try #1
INFO[0027] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.67]
DEBU[0027] [cleanup] Successfully cleaned up log links on host [172.27.116.67]
INFO[0027] [hosts] Successfully cleaned up host [172.27.116.67]
INFO[0027] [reconcile] Check etcd hosts to be added
DEBU[0027] [reconcile] Check worker hosts to be deleted
INFO[0027] [hosts] host [172.27.116.67] has another role, skipping delete from kubernetes cluster
INFO[0027] [worker] Tearing down Worker Plane..
INFO[0027] [worker] Host [172.27.116.67] is already a controlplane host, nothing to do.
INFO[0027] [worker] Successfully tore down Worker Plane..
INFO[0027] [hosts] Host [172.27.116.67] is already a controlplane or etcd host, skipping cleanup.
DEBU[0027] [reconcile] Check Control plane hosts to be deleted
INFO[0027] [hosts] Cordoning host [172.27.116.67]
DEBU[0027] Checking node list for node [ks-9047368], try #1
DEBU[0027] Checking node list for node [ks-9047368], try #1
DEBU[0027] Checking node list for node [ks-9047368], try #1
DEBU[0027] Node ks-9047368 is already cordoned: true
INFO[0027] [hosts] Deleting host [172.27.116.67] from the cluster
INFO[0027] [hosts] Successfully deleted host [172.27.116.67] from the cluster
INFO[0027] [controlplane] Tearing down the Controller Plane..
DEBU[0027] [remove/kube-apiserver] Checking if container is running on host [172.27.116.67]
DEBU[0027] [remove/kube-apiserver] Removing container on host [172.27.116.67]
INFO[0027] Removing container [kube-apiserver] on host [172.27.116.67], try #1
INFO[0031] [remove/kube-apiserver] Successfully removed container on host [172.27.116.67]
DEBU[0031] [remove/kube-controller-manager] Checking if container is running on host [172.27.116.67]
DEBU[0031] [remove/kube-controller-manager] Removing container on host [172.27.116.67]
INFO[0031] Removing container [kube-controller-manager] on host [172.27.116.67], try #1
INFO[0036] [remove/kube-controller-manager] Successfully removed container on host [172.27.116.67]
DEBU[0036] [remove/kube-scheduler] Checking if container is running on host [172.27.116.67]
DEBU[0036] [remove/kube-scheduler] Removing container on host [172.27.116.67]
INFO[0036] Removing container [kube-scheduler] on host [172.27.116.67], try #1
INFO[0043] [remove/kube-scheduler] Successfully removed container on host [172.27.116.67]
DEBU[0043] [remove/kubelet] Checking if container is running on host [172.27.116.67]
DEBU[0043] [remove/kubelet] Removing container on host [172.27.116.67]
INFO[0043] Removing container [kubelet] on host [172.27.116.67], try #1
INFO[0047] [remove/kubelet] Successfully removed container on host [172.27.116.67]
DEBU[0047] [remove/kube-proxy] Checking if container is running on host [172.27.116.67]
DEBU[0047] [remove/kube-proxy] Removing container on host [172.27.116.67]
INFO[0047] Removing container [kube-proxy] on host [172.27.116.67], try #1
INFO[0055] [remove/kube-proxy] Successfully removed container on host [172.27.116.67]
DEBU[0055] [remove/service-sidekick] Checking if container is running on host [172.27.116.67]
DEBU[0055] [remove/service-sidekick] Removing container on host [172.27.116.67]
INFO[0055] Removing container [service-sidekick] on host [172.27.116.67], try #1
INFO[0055] [remove/service-sidekick] Successfully removed container on host [172.27.116.67]
INFO[0055] [controlplane] Successfully tore down Controller Plane..
INFO[0055] [hosts] Cleaning up host [172.27.116.67]
DEBU[0055] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0055] [hosts] Running cleaner container on host [172.27.116.67]
DEBU[0055] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0055] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0056] Starting container [kube-cleaner] on host [172.27.116.67], try #1
INFO[0058] [kube-cleaner] Successfully started [kube-cleaner] container on host [172.27.116.67]
INFO[0058] Waiting for [kube-cleaner] container to exit on host [172.27.116.67]
DEBU[0059] Exit code for [kube-cleaner] container on host [172.27.116.67] is [0]
INFO[0059] [hosts] Removing cleaner container on host [172.27.116.67]
INFO[0059] Removing container [kube-cleaner] on host [172.27.116.67], try #1
INFO[0059] [hosts] Removing dead container logs on host [172.27.116.67]
DEBU[0059] [cleanup] Starting log link cleanup on host [172.27.116.67]
DEBU[0059] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.67]
DEBU[0059] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.67]
DEBU[0059] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0059] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0060] Starting container [rke-log-cleaner] on host [172.27.116.67], try #1
INFO[0061] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.67]
DEBU[0061] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.67]
DEBU[0062] [remove/rke-log-cleaner] Removing container on host [172.27.116.67]
INFO[0062] Removing container [rke-log-cleaner] on host [172.27.116.67], try #1
INFO[0063] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.67]
DEBU[0063] [cleanup] Successfully cleaned up log links on host [172.27.116.67]
INFO[0063] [hosts] Successfully cleaned up host [172.27.116.67]
INFO[0063] [reconcile] Rebuilding and updating local kube config
DEBU[0063] [reconcile] Rebuilding and updating local kube config, creating new kubeconfig
DEBU[0063] Deploying admin Kubeconfig locally at [./kube_config_cluster.yml]
INFO[0063] Successfully Deployed local admin kubeconfig at [./kube_config_cluster.yml]
DEBU[0063] [version] Using ./kube_config_cluster.yml to connect to Kubernetes cluster..
DEBU[0063] [version] Getting Kubernetes server version..
INFO[0063] [reconcile] host [172.27.116.65] is a control plane node with reachable Kubernetes API endpoint in the cluster
DEBU[0063] [restart/kube-apiserver] Checking if container is running on host [172.27.116.65]
DEBU[0063] [restart/kube-apiserver] Restarting container on host [172.27.116.65]
INFO[0063] Restarting container [kube-apiserver] on host [172.27.116.65], try #1
INFO[0071] [restart/kube-apiserver] Successfully restarted container on host [172.27.116.65]
DEBU[0071] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.65]
DEBU[0071] [restart/kube-controller-manager] Restarting container on host [172.27.116.65]
INFO[0071] Restarting container [kube-controller-manager] on host [172.27.116.65], try #1
INFO[0074] [restart/kube-controller-manager] Successfully restarted container on host [172.27.116.65]
DEBU[0074] [restart/kube-apiserver] Checking if container is running on host [172.27.116.66]
DEBU[0074] [restart/kube-apiserver] Restarting container on host [172.27.116.66]
INFO[0074] Restarting container [kube-apiserver] on host [172.27.116.66], try #1
INFO[0081] [restart/kube-apiserver] Successfully restarted container on host [172.27.116.66]
DEBU[0081] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.66]
DEBU[0081] [restart/kube-controller-manager] Restarting container on host [172.27.116.66]
INFO[0081] Restarting container [kube-controller-manager] on host [172.27.116.66], try #1
INFO[0084] [restart/kube-controller-manager] Successfully restarted container on host [172.27.116.66]
DEBU[0084] [restart/etcd] Checking if container is running on host [ks-9047489]
DEBU[0084] [restart/etcd] Restarting container on host [ks-9047489]
INFO[0084] Restarting container [etcd] on host [ks-9047489], try #1
INFO[0088] [restart/etcd] Successfully restarted container on host [ks-9047489]
DEBU[0088] [restart/etcd] Checking if container is running on host [ks-9047366]
DEBU[0088] [restart/etcd] Restarting container on host [ks-9047366]
INFO[0088] Restarting container [etcd] on host [ks-9047366], try #1
INFO[0093] [restart/etcd] Successfully restarted container on host [ks-9047366]
INFO[0093] [reconcile] Reconciled cluster state successfully
DEBU[0093] Provided value for maxUnavailable: {1 0 10%}
INFO[0093] max_unavailable_worker got rounded down to 0, resetting to 1
DEBU[0093] Parsed value of maxUnavailable: 1
DEBU[0093] Provided value for maxUnavailable: {0 1 }
DEBU[0093] Parsed value of maxUnavailable: 1
INFO[0093] Setting maxUnavailable for worker nodes to: 1
INFO[0093] Setting maxUnavailable for controlplane nodes to: 1
DEBU[0093] Encryption is disabled in both current and new spec; no action is required
INFO[0093] Pre-pulling kubernetes images
DEBU[0093] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65], try #1
DEBU[0093] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66], try #1
INFO[0093] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66]
INFO[0093] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65]
INFO[0093] Kubernetes images pulled successfully
DEBU[0093] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0093] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0093] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0093] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0093] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0093] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0093] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0093] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0093] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0093] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0093] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0093] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0093] [etcd] Building up etcd plane..
DEBU[0093] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0093] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0093] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0094] Starting container [etcd-fix-perm] on host [172.27.116.65], try #1
INFO[0097] Successfully started [etcd-fix-perm] container on host [172.27.116.65]
INFO[0097] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.65]
INFO[0097] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.65]
DEBU[0099] Exit code for [etcd-fix-perm] container on host [172.27.116.65] is [0]
DEBU[0099] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.65]
DEBU[0099] [remove/etcd-fix-perm] Removing container on host [172.27.116.65]
INFO[0099] Removing container [etcd-fix-perm] on host [172.27.116.65], try #1
INFO[0099] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.65]
DEBU[0099] [etcd] Container [etcd] is already running on host [172.27.116.65]
DEBU[0099] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.65]
DEBU[0099] slice is not equal, showing data in new value which is not in old value: map[--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380:{}]
DEBU[0099] slice is not equal, showing data in old value which is not in new value: map[--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380:{}]
DEBU[0099] [etcd] Container [etcd] is eligible for upgrade on host [172.27.116.65]
DEBU[0099] [etcd] Checking for deployed [etcd]
INFO[0099] Checking if container [etcd] is running on host [172.27.116.65], try #1
DEBU[0099] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.65], try #1
INFO[0099] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.65]
DEBU[0099] [etcd] Stopping old container
INFO[0099] Checking if container [old-etcd] is running on host [172.27.116.65], try #1
INFO[0099] Stopping container [etcd] on host [172.27.116.65] with stopTimeoutDuration [5s], try #1
INFO[0102] Waiting for [etcd] container to exit on host [172.27.116.65]
DEBU[0102] Exit code for [etcd] container on host [172.27.116.65] is [0]
INFO[0102] Renaming container [etcd] to [old-etcd] on host [172.27.116.65], try #1
DEBU[0102] [etcd] Successfully stopped old container etcd on host [172.27.116.65]
INFO[0103] Starting container [etcd] on host [172.27.116.65], try #1
INFO[0104] [etcd] Successfully updated [etcd] container on host [172.27.116.65]
DEBU[0104] [etcd] Removing old container
INFO[0104] Removing container [old-etcd] on host [172.27.116.65], try #1
DEBU[0104] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0104] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0104] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0104] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.65]
DEBU[0104] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.55:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0104] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.65]
DEBU[0104] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.65]
INFO[0104] Removing container [etcd-rolling-snapshots] on host [172.27.116.65], try #1
INFO[0106] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.65]
DEBU[0106] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0106] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
INFO[0107] Starting container [etcd-rolling-snapshots] on host [172.27.116.65], try #1
INFO[0108] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.65]
DEBU[0113] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0113] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0113] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
INFO[0113] Starting container [rke-bundle-cert] on host [172.27.116.65], try #1
INFO[0115] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.65]
INFO[0115] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.65]
DEBU[0116] Exit code for [rke-bundle-cert] container on host [172.27.116.65] is [0]
INFO[0116] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.65]
INFO[0116] Removing container [rke-bundle-cert] on host [172.27.116.65], try #1
DEBU[0116] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0116] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0116] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0116] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0116] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0117] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0119] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0119] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0120] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0120] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0120] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0120] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0120] [etcd] Creating log link for Container [etcd] on host [172.27.116.65]
DEBU[0120] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0120] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0120] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0120] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0121] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0123] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0123] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0124] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0124] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0124] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0124] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.65]
DEBU[0124] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0124] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0124] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0125] Starting container [etcd-fix-perm] on host [172.27.116.66], try #1
INFO[0126] Successfully started [etcd-fix-perm] container on host [172.27.116.66]
INFO[0126] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.66]
INFO[0126] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.66]
INFO[0126] Container [etcd-fix-perm] is still running on host [172.27.116.66]: stderr: [], stdout: []
INFO[0127] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.66]
DEBU[0128] Exit code for [etcd-fix-perm] container on host [172.27.116.66] is [0]
DEBU[0128] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.66]
DEBU[0128] [remove/etcd-fix-perm] Removing container on host [172.27.116.66]
INFO[0128] Removing container [etcd-fix-perm] on host [172.27.116.66], try #1
INFO[0128] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.66]
DEBU[0128] [etcd] Container [etcd] is already running on host [172.27.116.66]
DEBU[0128] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.66]
DEBU[0128] slice is not equal, showing data in new value which is not in old value: map[--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380:{}]
DEBU[0128] slice is not equal, showing data in old value which is not in new value: map[--initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380:{}]
DEBU[0128] [etcd] Container [etcd] is eligible for upgrade on host [172.27.116.66]
DEBU[0128] [etcd] Checking for deployed [etcd]
INFO[0128] Checking if container [etcd] is running on host [172.27.116.66], try #1
DEBU[0128] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.66], try #1
INFO[0128] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.66]
DEBU[0128] [etcd] Stopping old container
INFO[0128] Checking if container [old-etcd] is running on host [172.27.116.66], try #1
INFO[0128] Stopping container [etcd] on host [172.27.116.66] with stopTimeoutDuration [5s], try #1
INFO[0130] Waiting for [etcd] container to exit on host [172.27.116.66]
DEBU[0130] Exit code for [etcd] container on host [172.27.116.66] is [0]
INFO[0130] Renaming container [etcd] to [old-etcd] on host [172.27.116.66], try #1
DEBU[0130] [etcd] Successfully stopped old container etcd on host [172.27.116.66]
INFO[0131] Starting container [etcd] on host [172.27.116.66], try #1
INFO[0132] [etcd] Successfully updated [etcd] container on host [172.27.116.66]
DEBU[0132] [etcd] Removing old container
INFO[0132] Removing container [old-etcd] on host [172.27.116.66], try #1
DEBU[0132] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0132] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0132] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0132] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.66]
DEBU[0132] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.56:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0132] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.66]
DEBU[0132] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.66]
INFO[0132] Removing container [etcd-rolling-snapshots] on host [172.27.116.66], try #1
INFO[0134] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.66]
DEBU[0134] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0134] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
INFO[0135] Starting container [etcd-rolling-snapshots] on host [172.27.116.66], try #1
INFO[0136] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.66]
DEBU[0141] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0141] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0141] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
INFO[0142] Starting container [rke-bundle-cert] on host [172.27.116.66], try #1
INFO[0143] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.66]
INFO[0143] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.66]
DEBU[0144] Exit code for [rke-bundle-cert] container on host [172.27.116.66] is [0]
INFO[0144] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.66]
INFO[0144] Removing container [rke-bundle-cert] on host [172.27.116.66], try #1
DEBU[0144] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0144] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0144] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0144] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0144] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0145] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0147] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0147] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0149] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0149] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0149] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0149] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0149] [etcd] Creating log link for Container [etcd] on host [172.27.116.66]
DEBU[0149] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0149] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0149] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0149] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0151] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0153] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0153] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0154] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0154] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0154] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0154] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.66]
INFO[0154] [etcd] Successfully started etcd plane.. Checking etcd cluster health
DEBU[0154] [etcd] check etcd cluster health on host [172.27.116.65]
INFO[0154] [etcd] etcd host [172.27.116.65] reported healthy=true
DEBU[0154] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0154] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0154] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0154] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0154] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0154] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0154] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0154] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0154] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0154] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0154] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0154] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0154] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0154] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0154] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0154] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0154] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0154] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0154] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0154] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0154] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0154] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0154] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0154] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0154] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0154] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0154] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0154] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0154] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0154] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0154] [controlplane] Now checking status of node ks-9047489, try #1
DEBU[0154] Checking node list for node [ks-9047489], try #1
DEBU[0154] [controlplane] Found node by name ks-9047489
INFO[0154] [controlplane] Now checking status of node ks-9047366, try #1
DEBU[0154] Checking node list for node [ks-9047366], try #1
DEBU[0154] [controlplane] Found node by name ks-9047366
INFO[0154] [controlplane] Processing controlplane hosts for upgrade 1 at a time
INFO[0154] Processing controlplane host ks-9047489
INFO[0154] [controlplane] Now checking status of node ks-9047489, try #1
DEBU[0154] Checking node list for node [ks-9047489], try #1
DEBU[0154] [controlplane] Found node by name ks-9047489
INFO[0154] [controlplane] Getting list of nodes for upgrade
DEBU[0154] [controlplane] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.65]
DEBU[0154] [controlplane] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.65]
DEBU[0154] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.65]
DEBU[0154] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.55:2379,https://172.27.116.56:2379:{}]
DEBU[0154] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.57:2379:{}]
DEBU[0154] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.65]
DEBU[0154] [controlplane] Host ks-9047489 is upgradable because kube-apiserver has changed
DEBU[0154] [worker] Checking if container [nginx-proxy] is eligible for upgrade on host [172.27.116.65]
DEBU[0154] [worker] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.65]
DEBU[0154] [worker] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.65]
DEBU[0154] [worker] Checking if container [kubelet] is eligible for upgrade on host [172.27.116.65]
DEBU[0154] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0154] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0154] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0154] [worker] Container [kubelet] is not eligible for upgrade on host [172.27.116.65]
DEBU[0154] [worker] Checking if container [kube-proxy] is eligible for upgrade on host [172.27.116.65]
DEBU[0154] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0154] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0154] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0154] [worker] Container [kube-proxy] is not eligible for upgrade on host [172.27.116.65]
DEBU[0154] [worker] Host ks-9047489 is not upgradable
DEBU[0154] [controlplane] Cordoning node ks-9047489
DEBU[0154] Checking node list for node [ks-9047489], try #1
DEBU[0154] Checking node list for node [ks-9047489], try #1
DEBU[0154] Node ks-9047489 is already cordoned: true
INFO[0154] Upgrading controlplane components for control host ks-9047489
DEBU[0154] [remove/nginx-proxy] Checking if container is running on host [172.27.116.65]
DEBU[0154] [remove/nginx-proxy] Container doesn't exist on host [172.27.116.65]
INFO[0154] Checking if container [service-sidekick] is running on host [172.27.116.65], try #1
DEBU[0154] [sidekick] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.65]
DEBU[0154] [sidekick] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.65]
INFO[0154] [sidekick] Sidekick container already created on host [172.27.116.65]
DEBU[0154] [controlplane] Container [kube-apiserver] is already running on host [172.27.116.65]
DEBU[0154] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.65]
DEBU[0154] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.55:2379,https://172.27.116.56:2379:{}]
DEBU[0154] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.57:2379:{}]
DEBU[0154] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.65]
DEBU[0154] [controlplane] Checking for deployed [kube-apiserver]
INFO[0154] Checking if container [kube-apiserver] is running on host [172.27.116.65], try #1
DEBU[0154] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65], try #1
INFO[0154] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65]
DEBU[0154] [controlplane] Stopping old container
INFO[0154] Checking if container [old-kube-apiserver] is running on host [172.27.116.65], try #1
INFO[0154] Stopping container [kube-apiserver] on host [172.27.116.65] with stopTimeoutDuration [5s], try #1
INFO[0160] Waiting for [kube-apiserver] container to exit on host [172.27.116.65]
DEBU[0160] Exit code for [kube-apiserver] container on host [172.27.116.65] is [137]
INFO[0160] Renaming container [kube-apiserver] to [old-kube-apiserver] on host [172.27.116.65], try #1
DEBU[0160] [controlplane] Successfully stopped old container kube-apiserver on host [172.27.116.65]
INFO[0161] Starting container [kube-apiserver] on host [172.27.116.65], try #1
INFO[0162] [controlplane] Successfully updated [kube-apiserver] container on host [172.27.116.65]
DEBU[0162] [controlplane] Removing old container
INFO[0162] Removing container [old-kube-apiserver] on host [172.27.116.65], try #1
INFO[0165] [healthcheck] Start Healthcheck on service [kube-apiserver] on host [172.27.116.65]
DEBU[0166] [healthcheck] Service [kube-apiserver] is not healthy on host [172.27.116.65]. Response code: [403], response body: {"kind":"Status","apiVersion":"v1","metadata":{},"status":"Failure","message":"forbidden: User \"kube-apiserver\" cannot get path \"/healthz\"","reason":"Forbidden","details":{},"code":403}
, try #1
INFO[0171] [healthcheck] service [kube-apiserver] on host [172.27.116.65] is healthy
DEBU[0171] [controlplane] Creating log link for Container [kube-apiserver] on host [172.27.116.65]
DEBU[0171] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0171] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0171] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0171] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0172] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0173] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0173] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0174] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0174] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0175] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0175] [controlplane] Successfully created log link for Container [kube-apiserver] on host [172.27.116.65]
DEBU[0175] [controlplane] Container [kube-controller-manager] is already running on host [172.27.116.65]
DEBU[0175] [controlplane] Checking if container [kube-controller-manager] is eligible for upgrade on host [172.27.116.65]
DEBU[0175] [controlplane] Container [kube-controller-manager] is not eligible for upgrade on host [172.27.116.65]
INFO[0175] [healthcheck] Start Healthcheck on service [kube-controller-manager] on host [172.27.116.65]
INFO[0175] [healthcheck] service [kube-controller-manager] on host [172.27.116.65] is healthy
DEBU[0175] [controlplane] Creating log link for Container [kube-controller-manager] on host [172.27.116.65]
DEBU[0175] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0175] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0175] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0175] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0176] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0177] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0177] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0178] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0178] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0179] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0179] [controlplane] Successfully created log link for Container [kube-controller-manager] on host [172.27.116.65]
DEBU[0179] [controlplane] Container [kube-scheduler] is already running on host [172.27.116.65]
DEBU[0179] [controlplane] Checking if container [kube-scheduler] is eligible for upgrade on host [172.27.116.65]
DEBU[0179] [controlplane] Container [kube-scheduler] is not eligible for upgrade on host [172.27.116.65]
INFO[0179] [healthcheck] Start Healthcheck on service [kube-scheduler] on host [172.27.116.65]
INFO[0179] [healthcheck] service [kube-scheduler] on host [172.27.116.65] is healthy
DEBU[0179] [controlplane] Creating log link for Container [kube-scheduler] on host [172.27.116.65]
DEBU[0179] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0179] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0179] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0179] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0180] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0181] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0181] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0182] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0182] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0182] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0182] [controlplane] Successfully created log link for Container [kube-scheduler] on host [172.27.116.65]
INFO[0182] [controlplane] Now checking status of node ks-9047489, try #1
DEBU[0182] Checking node list for node [ks-9047489], try #1
DEBU[0182] [controlplane] Found node by name ks-9047489
DEBU[0182] Checking node list for node [ks-9047489], try #1
DEBU[0182] Checking node list for node [ks-9047489], try #1
DEBU[0182] Node ks-9047489 is already cordoned: false
INFO[0182] Processing controlplane host ks-9047366
INFO[0182] [controlplane] Now checking status of node ks-9047366, try #1
DEBU[0182] Checking node list for node [ks-9047366], try #1
DEBU[0182] [controlplane] Found node by name ks-9047366
INFO[0182] [controlplane] Getting list of nodes for upgrade
DEBU[0182] [controlplane] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.66]
DEBU[0182] [controlplane] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.66]
DEBU[0182] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.66]
DEBU[0182] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.56:2379,https://172.27.116.55:2379:{}]
DEBU[0182] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.56:2379,https://172.27.116.55:2379,https://172.27.116.57:2379:{}]
DEBU[0182] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.66]
DEBU[0182] [controlplane] Host ks-9047366 is upgradable because kube-apiserver has changed
DEBU[0182] [worker] Checking if container [nginx-proxy] is eligible for upgrade on host [172.27.116.66]
DEBU[0182] [worker] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.66]
DEBU[0182] [worker] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.66]
DEBU[0182] [worker] Checking if container [kubelet] is eligible for upgrade on host [172.27.116.66]
DEBU[0182] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0182] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0182] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0182] [worker] Container [kubelet] is not eligible for upgrade on host [172.27.116.66]
DEBU[0182] [worker] Checking if container [kube-proxy] is eligible for upgrade on host [172.27.116.66]
DEBU[0182] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0182] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0182] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0182] [worker] Container [kube-proxy] is not eligible for upgrade on host [172.27.116.66]
DEBU[0182] [worker] Host ks-9047366 is not upgradable
DEBU[0182] [controlplane] Cordoning node ks-9047366
DEBU[0182] Checking node list for node [ks-9047366], try #1
DEBU[0182] Checking node list for node [ks-9047366], try #1
DEBU[0182] Node ks-9047366 is already cordoned: true
INFO[0182] Upgrading controlplane components for control host ks-9047366
DEBU[0182] [remove/nginx-proxy] Checking if container is running on host [172.27.116.66]
DEBU[0182] [remove/nginx-proxy] Container doesn't exist on host [172.27.116.66]
INFO[0182] Checking if container [service-sidekick] is running on host [172.27.116.66], try #1
DEBU[0182] [sidekick] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.66]
DEBU[0182] [sidekick] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.66]
INFO[0182] [sidekick] Sidekick container already created on host [172.27.116.66]
DEBU[0182] [controlplane] Container [kube-apiserver] is already running on host [172.27.116.66]
DEBU[0182] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.66]
DEBU[0182] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.56:2379,https://172.27.116.55:2379:{}]
DEBU[0182] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.56:2379,https://172.27.116.55:2379,https://172.27.116.57:2379:{}]
DEBU[0182] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.66]
DEBU[0182] [controlplane] Checking for deployed [kube-apiserver]
INFO[0182] Checking if container [kube-apiserver] is running on host [172.27.116.66], try #1
DEBU[0182] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66], try #1
INFO[0182] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66]
DEBU[0182] [controlplane] Stopping old container
INFO[0182] Checking if container [old-kube-apiserver] is running on host [172.27.116.66], try #1
INFO[0182] Stopping container [kube-apiserver] on host [172.27.116.66] with stopTimeoutDuration [5s], try #1
INFO[0189] Waiting for [kube-apiserver] container to exit on host [172.27.116.66]
DEBU[0189] Exit code for [kube-apiserver] container on host [172.27.116.66] is [137]
INFO[0189] Renaming container [kube-apiserver] to [old-kube-apiserver] on host [172.27.116.66], try #1
DEBU[0189] [controlplane] Successfully stopped old container kube-apiserver on host [172.27.116.66]
INFO[0190] Starting container [kube-apiserver] on host [172.27.116.66], try #1
INFO[0193] [controlplane] Successfully updated [kube-apiserver] container on host [172.27.116.66]
DEBU[0193] [controlplane] Removing old container
INFO[0193] Removing container [old-kube-apiserver] on host [172.27.116.66], try #1
INFO[0197] [healthcheck] Start Healthcheck on service [kube-apiserver] on host [172.27.116.66]
DEBU[0198] [healthcheck] Service [kube-apiserver] is not healthy on host [172.27.116.66]. Response code: [500], response body: [+]ping ok
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
[+]poststarthook/priority-and-fairness-config-producer ok
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
INFO[0203] [healthcheck] service [kube-apiserver] on host [172.27.116.66] is healthy
DEBU[0203] [controlplane] Creating log link for Container [kube-apiserver] on host [172.27.116.66]
DEBU[0203] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0203] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0203] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0203] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0204] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0206] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0206] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0207] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0207] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0208] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0208] [controlplane] Successfully created log link for Container [kube-apiserver] on host [172.27.116.66]
DEBU[0208] [controlplane] Container [kube-controller-manager] is already running on host [172.27.116.66]
DEBU[0208] [controlplane] Checking if container [kube-controller-manager] is eligible for upgrade on host [172.27.116.66]
DEBU[0208] [controlplane] Container [kube-controller-manager] is not eligible for upgrade on host [172.27.116.66]
INFO[0208] [healthcheck] Start Healthcheck on service [kube-controller-manager] on host [172.27.116.66]
INFO[0208] [healthcheck] service [kube-controller-manager] on host [172.27.116.66] is healthy
DEBU[0208] [controlplane] Creating log link for Container [kube-controller-manager] on host [172.27.116.66]
DEBU[0208] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0208] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0208] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0208] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0209] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0211] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0211] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0212] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0212] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0212] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0212] [controlplane] Successfully created log link for Container [kube-controller-manager] on host [172.27.116.66]
DEBU[0212] [controlplane] Container [kube-scheduler] is already running on host [172.27.116.66]
DEBU[0212] [controlplane] Checking if container [kube-scheduler] is eligible for upgrade on host [172.27.116.66]
DEBU[0212] [controlplane] Container [kube-scheduler] is not eligible for upgrade on host [172.27.116.66]
INFO[0212] [healthcheck] Start Healthcheck on service [kube-scheduler] on host [172.27.116.66]
INFO[0213] [healthcheck] service [kube-scheduler] on host [172.27.116.66] is healthy
DEBU[0213] [controlplane] Creating log link for Container [kube-scheduler] on host [172.27.116.66]
DEBU[0213] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0213] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0213] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0213] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0214] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0216] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0216] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0218] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0218] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0218] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0218] [controlplane] Successfully created log link for Container [kube-scheduler] on host [172.27.116.66]
INFO[0218] [controlplane] Now checking status of node ks-9047366, try #1
DEBU[0218] Checking node list for node [ks-9047366], try #1
DEBU[0218] [controlplane] Found node by name ks-9047366
DEBU[0218] Checking node list for node [ks-9047366], try #1
DEBU[0218] Checking node list for node [ks-9047366], try #1
DEBU[0218] Node ks-9047366 is already cordoned: false
INFO[0218] [controlplane] Successfully upgraded Controller Plane..
DEBU[0218] Checking if cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0218] Cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0218] Enabling kube-api audit log for cluster version [v1.22.10-rancher1-1]
DEBU[0218] Host: 172.27.116.65 has role: etcd
DEBU[0218] Host: 172.27.116.65 has role: controlplane
DEBU[0218] Host: 172.27.116.65 has role: worker
DEBU[0218] Host: 172.27.116.66 has role: etcd
DEBU[0218] Host: 172.27.116.66 has role: controlplane
DEBU[0218] Host: 172.27.116.66 has role: worker
INFO[0218] [authz] Creating rke-job-deployer ServiceAccount
INFO[0219] [authz] rke-job-deployer ServiceAccount created successfully
INFO[0219] [authz] Creating system:node ClusterRoleBinding
INFO[0219] [authz] system:node ClusterRoleBinding created successfully
INFO[0219] [authz] Creating kube-apiserver proxy ClusterRole and ClusterRoleBinding
INFO[0219] [authz] kube-apiserver proxy ClusterRole and ClusterRoleBinding created successfully
INFO[0219] Successfully Deployed state file at [./cluster.rkestate]
INFO[0219] [state] Saving full cluster state to Kubernetes
INFO[0219] [state] Successfully Saved full cluster state to Kubernetes ConfigMap: full-cluster-state
DEBU[0219] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0219] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0219] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0219] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0219] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0219] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0219] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0219] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0219] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0219] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0219] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0219] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0219] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0219] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0219] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0219] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0219] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0219] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0219] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0219] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0219] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0219] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0219] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0219] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0219] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0219] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0219] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0219] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0219] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0219] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0219] [worker] Upgrading Worker Plane..
INFO[0219] [worker] Successfully upgraded Worker Plane..
DEBU[0219] [cleanup] Starting log link cleanup on host [172.27.116.66]
DEBU[0219] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.66]
DEBU[0219] [cleanup] Starting log link cleanup on host [172.27.116.65]
DEBU[0219] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.65]
DEBU[0219] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.66]
DEBU[0219] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.65]
DEBU[0219] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
DEBU[0219] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0219] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0219] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0220] Starting container [rke-log-cleaner] on host [172.27.116.65], try #1
INFO[0220] Starting container [rke-log-cleaner] on host [172.27.116.66], try #1
INFO[0221] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.65]
DEBU[0221] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.65]
DEBU[0223] [remove/rke-log-cleaner] Removing container on host [172.27.116.65]
INFO[0223] Removing container [rke-log-cleaner] on host [172.27.116.65], try #1
INFO[0223] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.65]
DEBU[0223] [cleanup] Successfully cleaned up log links on host [172.27.116.65]
INFO[0223] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.66]
DEBU[0223] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.66]
DEBU[0227] [remove/rke-log-cleaner] Removing container on host [172.27.116.66]
INFO[0227] Removing container [rke-log-cleaner] on host [172.27.116.66], try #1
INFO[0228] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.66]
DEBU[0228] [cleanup] Successfully cleaned up log links on host [172.27.116.66]
INFO[0228] [sync] Syncing nodes Labels and Taints
DEBU[0228] worker [9] starting sync for node [ks-9047489]
DEBU[0228] Checking node list for node [ks-9047489], try #1
DEBU[0228] worker [0] starting sync for node [ks-9047366]
DEBU[0228] Checking node list for node [ks-9047366], try #1
DEBU[0228] skipping syncing labels for node [ks-9047489]
DEBU[0228] skipping syncing labels for node [ks-9047366]
INFO[0228] [sync] Successfully synced nodes Labels and Taints
DEBU[0228] Checking if cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0228] Cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0228] Enabling kube-api audit log for cluster version [v1.22.10-rancher1-1]
DEBU[0228] Host: 172.27.116.65 has role: etcd
DEBU[0228] Host: 172.27.116.65 has role: controlplane
DEBU[0228] Host: 172.27.116.65 has role: worker
DEBU[0228] Host: 172.27.116.66 has role: etcd
DEBU[0228] Host: 172.27.116.66 has role: controlplane
DEBU[0228] Host: 172.27.116.66 has role: worker
INFO[0228] [network] Setting up network plugin: flannel
INFO[0228] [addons] Saving ConfigMap for addon rke-network-plugin to Kubernetes
INFO[0228] [addons] Successfully saved ConfigMap for addon rke-network-plugin to Kubernetes
INFO[0228] [addons] Executing deploy job rke-network-plugin
DEBU[0228] Checking node list for node [ks-9047489], try #1
DEBU[0228] Checking addon job OS label for cluster version [v1.22.10-rancher1-1]
DEBU[0228] Cluster version [v1.22.10-rancher1-1] needs to use new OS label
DEBU[0229] [k8s] Job rke-network-plugin-deploy-job already exists..
INFO[0229] [addons] Setting up coredns
INFO[0229] [addons] Saving ConfigMap for addon rke-coredns-addon to Kubernetes
INFO[0229] [addons] Successfully saved ConfigMap for addon rke-coredns-addon to Kubernetes
INFO[0229] [addons] Executing deploy job rke-coredns-addon
DEBU[0229] Checking node list for node [ks-9047489], try #1
DEBU[0229] Checking addon job OS label for cluster version [v1.22.10-rancher1-1]
DEBU[0229] Cluster version [v1.22.10-rancher1-1] needs to use new OS label
DEBU[0229] [k8s] Job rke-coredns-addon-deploy-job already exists..
INFO[0229] [addons] CoreDNS deployed successfully
INFO[0229] [dns] DNS provider coredns deployed successfully
INFO[0229] [addons] Setting up Metrics Server
INFO[0229] [addons] Saving ConfigMap for addon rke-metrics-addon to Kubernetes
INFO[0229] [addons] Successfully saved ConfigMap for addon rke-metrics-addon to Kubernetes
INFO[0229] [addons] Executing deploy job rke-metrics-addon
DEBU[0229] Checking node list for node [ks-9047489], try #1
DEBU[0229] Checking addon job OS label for cluster version [v1.22.10-rancher1-1]
DEBU[0229] Cluster version [v1.22.10-rancher1-1] needs to use new OS label
DEBU[0229] [k8s] Job rke-metrics-addon-deploy-job already exists..
INFO[0229] [addons] Metrics Server deployed successfully
INFO[0229] [ingress] Setting up nginx ingress controller
INFO[0229] [ingress] removing admission batch jobs if they exist
INFO[0229] [addons] Saving ConfigMap for addon rke-ingress-controller to Kubernetes
INFO[0229] [addons] Successfully saved ConfigMap for addon rke-ingress-controller to Kubernetes
INFO[0229] [addons] Executing deploy job rke-ingress-controller
DEBU[0229] Checking node list for node [ks-9047489], try #1
DEBU[0229] Checking addon job OS label for cluster version [v1.22.10-rancher1-1]
DEBU[0229] Cluster version [v1.22.10-rancher1-1] needs to use new OS label
DEBU[0229] [k8s] Job rke-ingress-controller-deploy-job already exists..
INFO[0229] [ingress] removing default backend service and deployment if they exist
INFO[0229] [ingress] ingress controller nginx deployed successfully
INFO[0229] [addons] Setting up user addons
INFO[0229] [addons] no user addons defined
INFO[0229] Finished building Kubernetes cluster successfully
root@ks-9047489:~#

```  