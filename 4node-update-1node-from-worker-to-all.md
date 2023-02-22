
There are 4 nodes consist of one cluster.  
+ ks-9047489 (172.27.116.65/172.27.116.55) (etcd, controlplane, worker)  
+ ks-9047366 (172.27.116.66/172.27.116.56) (etcd, controlplane, worker)  
+ ks-9047368 (172.27.116.67/172.27.116.57) (etcd, controlplane, worker)  
+ `ks-9047988` (172.27.116.68/172.27.116.58) (worker)  

We use rke tool to update ks-9047988 node role from `worker` to `all` roles.  
There is the debug log on below.  

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
DEBU[0000] Host: 172.27.116.68 has role: etcd
DEBU[0000] Host: 172.27.116.68 has role: controlplane
DEBU[0000] Host: 172.27.116.68 has role: worker
DEBU[0000] [state] previous state found, this is not a legacy cluster
INFO[0000] [certificates] GenerateServingCertificate is disabled, checking if there are unused kubelet certificates
INFO[0000] [certificates] Generating Kubernetes API server certificates
INFO[0000] [certificates] Generating admin certificates and kubeconfig
INFO[0000] [certificates] Generating kube-etcd-172-27-116-55 certificate and key
INFO[0000] [certificates] Generating kube-etcd-172-27-116-56 certificate and key
INFO[0000] [certificates] Generating kube-etcd-172-27-116-57 certificate and key
INFO[0000] [certificates] Generating kube-etcd-172-27-116-58 certificate and key
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
DEBU[0000] Host: 172.27.116.68 has role: etcd
DEBU[0000] Host: 172.27.116.68 has role: controlplane
DEBU[0000] Host: 172.27.116.68 has role: worker
INFO[0000] Building Kubernetes cluster
INFO[0000] [dialer] Setup tunnel for host [172.27.116.68]
INFO[0000] [dialer] Setup tunnel for host [172.27.116.65]
INFO[0000] [dialer] Setup tunnel for host [172.27.116.66]
INFO[0000] [dialer] Setup tunnel for host [172.27.116.67]
DEBU[0000] Connecting to Docker API for host [172.27.116.66]
DEBU[0000] Connecting to Docker API for host [172.27.116.68]
DEBU[0000] Connecting to Docker API for host [172.27.116.67]
DEBU[0000] Connecting to Docker API for host [172.27.116.65]
DEBU[0000] Docker Info found for host [172.27.116.66]: types.Info{ID:"7T67:DXEC:PYY6:VISK:5RG4:M2UV:N6NE:MAI4:QNBJ:PXN6:JNZ3:E6XT", Containers:43, ContainersRunning:41, ContainersPaused:0, ContainersStopped:2, Images:43, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:156, OomKillDisable:true, NGoroutines:138, SystemTime:"2023-02-22T14:44:17.855668891+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc000411ab0), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047366", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
DEBU[0000] Docker Info found for host [172.27.116.68]: types.Info{ID:"MXKP:YT7W:POR5:IYHK:3IPJ:MTDH:K2AG:IP7X:6M66:73HM:XICA:XUTP", Containers:72, ContainersRunning:42, ContainersPaused:0, ContainersStopped:30, Images:31, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:252, OomKillDisable:true, NGoroutines:206, SystemTime:"2023-02-22T14:44:17.989602411+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc0004100e0), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047988", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
DEBU[0000] Docker Info found for host [172.27.116.67]: types.Info{ID:"VN5L:TH7K:7SRQ:LLCZ:F7QU:TJUR:7AZ7:ETFA:NIKN:KE4N:OEJE:KWUZ", Containers:47, ContainersRunning:42, ContainersPaused:0, ContainersStopped:5, Images:31, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:175, OomKillDisable:true, NGoroutines:153, SystemTime:"2023-02-22T14:44:18.744353743+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc0000b00e0), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047368", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
DEBU[0000] Docker Info found for host [172.27.116.65]: types.Info{ID:"PXEX:4WFR:EIA2:YQWO:7QYJ:AV77:D5FS:5CXU:O7VZ:7V3L:V24Y:IHH2", Containers:136, ContainersRunning:97, ContainersPaused:0, ContainersStopped:39, Images:46, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:457, OomKillDisable:true, NGoroutines:361, SystemTime:"2023-02-22T14:44:18.300588792+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc0000b03f0), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047489", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
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
DEBU[0000] Host: 172.27.116.68 has role: worker
INFO[0000] [network] Deploying port listener containers
DEBU[0000] [network] Starting deployListener [rke-etcd-port-listener] on host [172.27.116.66]
DEBU[0000] [network] Starting deployListener [rke-etcd-port-listener] on host [172.27.116.65]
DEBU[0000] [network] Starting deployListener [rke-etcd-port-listener] on host [172.27.116.68]
DEBU[0000] [network] Starting deployListener [rke-etcd-port-listener] on host [172.27.116.67]
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
DEBU[0000] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0000] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0000] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0000] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0000] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0001] Starting container [rke-etcd-port-listener] on host [172.27.116.65], try #1
INFO[0002] Starting container [rke-etcd-port-listener] on host [172.27.116.66], try #1
INFO[0002] Starting container [rke-etcd-port-listener] on host [172.27.116.68], try #1
INFO[0003] Starting container [rke-etcd-port-listener] on host [172.27.116.67], try #1
DEBU[0003] [network] Service is already up on host [172.27.116.65]
DEBU[0004] [network] Service is already up on host [172.27.116.66]
INFO[0004] [network] Successfully started [rke-etcd-port-listener] container on host [172.27.116.68]
DEBU[0004] [network] Service is already up on host [172.27.116.67]
DEBU[0004] [network] Starting deployListener [rke-cp-port-listener] on host [172.27.116.67]
DEBU[0004] [network] Starting deployListener [rke-cp-port-listener] on host [172.27.116.65]
DEBU[0004] [network] Starting deployListener [rke-cp-port-listener] on host [172.27.116.66]
DEBU[0004] [network] Starting deployListener [rke-cp-port-listener] on host [172.27.116.68]
DEBU[0004] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
DEBU[0004] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
DEBU[0004] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
DEBU[0004] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0004] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0004] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0004] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0004] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0005] Starting container [rke-cp-port-listener] on host [172.27.116.65], try #1
INFO[0005] Starting container [rke-cp-port-listener] on host [172.27.116.68], try #1
INFO[0006] Starting container [rke-cp-port-listener] on host [172.27.116.66], try #1
INFO[0006] Starting container [rke-cp-port-listener] on host [172.27.116.67], try #1
DEBU[0006] [network] Service is already up on host [172.27.116.65]
DEBU[0007] [network] Service is already up on host [172.27.116.68]
DEBU[0007] [network] Service is already up on host [172.27.116.66]
DEBU[0007] [network] Service is already up on host [172.27.116.67]
DEBU[0007] [network] Starting deployListener [rke-worker-port-listener] on host [172.27.116.65]
DEBU[0007] [network] Starting deployListener [rke-worker-port-listener] on host [172.27.116.67]
DEBU[0007] [network] Starting deployListener [rke-worker-port-listener] on host [172.27.116.68]
DEBU[0007] [network] Starting deployListener [rke-worker-port-listener] on host [172.27.116.66]
DEBU[0007] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
DEBU[0007] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
DEBU[0007] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
DEBU[0007] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0007] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0007] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0007] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0007] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0008] Starting container [rke-worker-port-listener] on host [172.27.116.65], try #1
INFO[0009] Starting container [rke-worker-port-listener] on host [172.27.116.68], try #1
INFO[0009] Starting container [rke-worker-port-listener] on host [172.27.116.66], try #1
INFO[0010] Starting container [rke-worker-port-listener] on host [172.27.116.67], try #1
DEBU[0010] [network] Service is already up on host [172.27.116.65]
DEBU[0010] [network] Service is already up on host [172.27.116.68]
DEBU[0011] [network] Service is already up on host [172.27.116.66]
DEBU[0011] [network] Service is already up on host [172.27.116.67]
INFO[0011] [network] Port listener containers deployed successfully
INFO[0011] [network] Running etcd <-> etcd port checks
INFO[0011] [network] Checking if host [172.27.116.65] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [2379 2380], try #1
DEBU[0011] [remove/rke-port-checker] Checking if container is running on host [172.27.116.65]
INFO[0011] [network] Checking if host [172.27.116.66] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [2379 2380], try #1
DEBU[0011] [remove/rke-port-checker] Checking if container is running on host [172.27.116.66]
INFO[0011] [network] Checking if host [172.27.116.67] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [2379 2380], try #1
DEBU[0011] [remove/rke-port-checker] Checking if container is running on host [172.27.116.67]
INFO[0011] [network] Checking if host [172.27.116.68] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [2379 2380], try #1
DEBU[0011] [remove/rke-port-checker] Checking if container is running on host [172.27.116.68]
DEBU[0011] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.65]
DEBU[0011] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.66]
DEBU[0011] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.67]
DEBU[0011] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.68]
DEBU[0011] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
DEBU[0011] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
DEBU[0011] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
DEBU[0011] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0011] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0011] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0011] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0011] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0012] Starting container [rke-port-checker] on host [172.27.116.68], try #1
INFO[0012] Starting container [rke-port-checker] on host [172.27.116.65], try #1
INFO[0013] Starting container [rke-port-checker] on host [172.27.116.67], try #1
INFO[0013] [network] Successfully started [rke-port-checker] container on host [172.27.116.68]
INFO[0013] [network] Successfully started [rke-port-checker] container on host [172.27.116.65]
INFO[0013] Starting container [rke-port-checker] on host [172.27.116.66], try #1
DEBU[0014] [network] containerLog [] on host: 172.27.116.65
INFO[0014] Removing container [rke-port-checker] on host [172.27.116.65], try #1
DEBU[0014] [network] containerLog [] on host: 172.27.116.68
INFO[0014] Removing container [rke-port-checker] on host [172.27.116.68], try #1
DEBU[0014] [network] Length of containerLog is [0] on host: 172.27.116.68
INFO[0014] [network] Successfully started [rke-port-checker] container on host [172.27.116.67]
DEBU[0015] [network] Length of containerLog is [0] on host: 172.27.116.65
INFO[0016] [network] Successfully started [rke-port-checker] container on host [172.27.116.66]
DEBU[0016] [network] containerLog [] on host: 172.27.116.67
INFO[0016] Removing container [rke-port-checker] on host [172.27.116.67], try #1
DEBU[0017] [network] Length of containerLog is [0] on host: 172.27.116.67
DEBU[0017] [network] containerLog [] on host: 172.27.116.66
INFO[0017] Removing container [rke-port-checker] on host [172.27.116.66], try #1
DEBU[0018] [network] Length of containerLog is [0] on host: 172.27.116.66
INFO[0018] [network] Running control plane -> etcd port checks
INFO[0018] [network] Checking if host [172.27.116.65] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [2379], try #1
DEBU[0018] [remove/rke-port-checker] Checking if container is running on host [172.27.116.65]
INFO[0018] [network] Checking if host [172.27.116.66] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [2379], try #1
DEBU[0018] [remove/rke-port-checker] Checking if container is running on host [172.27.116.66]
INFO[0018] [network] Checking if host [172.27.116.67] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [2379], try #1
DEBU[0018] [remove/rke-port-checker] Checking if container is running on host [172.27.116.67]
INFO[0018] [network] Checking if host [172.27.116.68] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [2379], try #1
DEBU[0018] [remove/rke-port-checker] Checking if container is running on host [172.27.116.68]
DEBU[0018] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.65]
DEBU[0018] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.66]
DEBU[0018] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.68]
DEBU[0018] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.67]
DEBU[0018] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
DEBU[0018] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
DEBU[0018] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
DEBU[0018] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0018] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0018] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0018] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0018] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0019] Starting container [rke-port-checker] on host [172.27.116.68], try #1
INFO[0019] Starting container [rke-port-checker] on host [172.27.116.65], try #1
INFO[0020] Starting container [rke-port-checker] on host [172.27.116.67], try #1
INFO[0020] [network] Successfully started [rke-port-checker] container on host [172.27.116.68]
INFO[0020] [network] Successfully started [rke-port-checker] container on host [172.27.116.65]
INFO[0020] Starting container [rke-port-checker] on host [172.27.116.66], try #1
INFO[0021] [network] Successfully started [rke-port-checker] container on host [172.27.116.67]
DEBU[0021] [network] containerLog [] on host: 172.27.116.68
INFO[0021] Removing container [rke-port-checker] on host [172.27.116.68], try #1
DEBU[0021] [network] containerLog [] on host: 172.27.116.65
INFO[0021] Removing container [rke-port-checker] on host [172.27.116.65], try #1
DEBU[0021] [network] Length of containerLog is [0] on host: 172.27.116.68
DEBU[0021] [network] Length of containerLog is [0] on host: 172.27.116.65
INFO[0022] [network] Successfully started [rke-port-checker] container on host [172.27.116.66]
DEBU[0023] [network] containerLog [] on host: 172.27.116.67
INFO[0023] Removing container [rke-port-checker] on host [172.27.116.67], try #1
DEBU[0023] [network] Length of containerLog is [0] on host: 172.27.116.67
DEBU[0024] [network] containerLog [] on host: 172.27.116.66
INFO[0024] Removing container [rke-port-checker] on host [172.27.116.66], try #1
DEBU[0025] [network] Length of containerLog is [0] on host: 172.27.116.66
INFO[0025] [network] Running control plane -> worker port checks
INFO[0025] [network] Checking if host [172.27.116.68] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [10250], try #1
DEBU[0025] [remove/rke-port-checker] Checking if container is running on host [172.27.116.68]
INFO[0025] [network] Checking if host [172.27.116.67] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [10250], try #1
INFO[0025] [network] Checking if host [172.27.116.66] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [10250], try #1
INFO[0025] [network] Checking if host [172.27.116.65] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [10250], try #1
DEBU[0025] [remove/rke-port-checker] Checking if container is running on host [172.27.116.65]
DEBU[0025] [remove/rke-port-checker] Checking if container is running on host [172.27.116.67]
DEBU[0025] [remove/rke-port-checker] Checking if container is running on host [172.27.116.66]
DEBU[0025] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.65]
DEBU[0025] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.66]
DEBU[0025] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.67]
DEBU[0025] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.68]
DEBU[0025] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
DEBU[0025] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
DEBU[0025] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
DEBU[0025] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0025] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0025] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0025] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0025] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0025] Starting container [rke-port-checker] on host [172.27.116.68], try #1
INFO[0025] Starting container [rke-port-checker] on host [172.27.116.65], try #1
INFO[0026] Starting container [rke-port-checker] on host [172.27.116.67], try #1
INFO[0026] [network] Successfully started [rke-port-checker] container on host [172.27.116.68]
INFO[0026] [network] Successfully started [rke-port-checker] container on host [172.27.116.65]
INFO[0027] Starting container [rke-port-checker] on host [172.27.116.66], try #1
DEBU[0027] [network] containerLog [] on host: 172.27.116.65
INFO[0027] Removing container [rke-port-checker] on host [172.27.116.65], try #1
INFO[0027] [network] Successfully started [rke-port-checker] container on host [172.27.116.67]
DEBU[0028] [network] Length of containerLog is [0] on host: 172.27.116.65
DEBU[0029] [network] containerLog [] on host: 172.27.116.68
INFO[0029] Removing container [rke-port-checker] on host [172.27.116.68], try #1
DEBU[0029] [network] containerLog [] on host: 172.27.116.67
INFO[0029] Removing container [rke-port-checker] on host [172.27.116.67], try #1
INFO[0029] [network] Successfully started [rke-port-checker] container on host [172.27.116.66]
DEBU[0029] [network] Length of containerLog is [0] on host: 172.27.116.68
DEBU[0030] [network] Length of containerLog is [0] on host: 172.27.116.67
DEBU[0030] [network] containerLog [] on host: 172.27.116.66
INFO[0030] Removing container [rke-port-checker] on host [172.27.116.66], try #1
DEBU[0031] [network] Length of containerLog is [0] on host: 172.27.116.66
INFO[0031] [network] Running workers -> control plane port checks
INFO[0031] [network] Checking if host [172.27.116.66] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [6443], try #1
INFO[0031] [network] Checking if host [172.27.116.67] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [6443], try #1
DEBU[0031] [remove/rke-port-checker] Checking if container is running on host [172.27.116.67]
DEBU[0031] [remove/rke-port-checker] Checking if container is running on host [172.27.116.66]
INFO[0031] [network] Checking if host [172.27.116.68] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [6443], try #1
DEBU[0031] [remove/rke-port-checker] Checking if container is running on host [172.27.116.68]
INFO[0031] [network] Checking if host [172.27.116.65] can connect to host(s) [172.27.116.55 172.27.116.56 172.27.116.57 172.27.116.58] on port(s) [6443], try #1
DEBU[0031] [remove/rke-port-checker] Checking if container is running on host [172.27.116.65]
DEBU[0031] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.65]
DEBU[0031] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.66]
DEBU[0031] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.67]
DEBU[0031] [remove/rke-port-checker] Container doesn't exist on host [172.27.116.68]
DEBU[0031] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
DEBU[0031] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
DEBU[0031] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
DEBU[0031] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0031] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0031] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0031] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0031] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0032] Starting container [rke-port-checker] on host [172.27.116.67], try #1
INFO[0033] Starting container [rke-port-checker] on host [172.27.116.65], try #1
INFO[0033] Starting container [rke-port-checker] on host [172.27.116.68], try #1
INFO[0033] Starting container [rke-port-checker] on host [172.27.116.66], try #1
INFO[0034] [network] Successfully started [rke-port-checker] container on host [172.27.116.65]
INFO[0034] [network] Successfully started [rke-port-checker] container on host [172.27.116.67]
INFO[0034] [network] Successfully started [rke-port-checker] container on host [172.27.116.68]
DEBU[0034] [network] containerLog [] on host: 172.27.116.65
INFO[0034] Removing container [rke-port-checker] on host [172.27.116.65], try #1
INFO[0035] [network] Successfully started [rke-port-checker] container on host [172.27.116.66]
DEBU[0035] [network] containerLog [] on host: 172.27.116.67
INFO[0035] Removing container [rke-port-checker] on host [172.27.116.67], try #1
DEBU[0035] [network] containerLog [] on host: 172.27.116.68
INFO[0035] Removing container [rke-port-checker] on host [172.27.116.68], try #1
DEBU[0035] [network] Length of containerLog is [0] on host: 172.27.116.65
DEBU[0035] [network] Length of containerLog is [0] on host: 172.27.116.68
DEBU[0036] [network] Length of containerLog is [0] on host: 172.27.116.67
DEBU[0037] [network] containerLog [] on host: 172.27.116.66
INFO[0037] Removing container [rke-port-checker] on host [172.27.116.66], try #1
DEBU[0038] [network] Length of containerLog is [0] on host: 172.27.116.66
INFO[0038] [network] Checking KubeAPI port Control Plane hosts
DEBU[0038] [network] Checking KubeAPI port [6443] on host: 172.27.116.65
DEBU[0038] [network] Checking KubeAPI port [6443] on host: 172.27.116.66
DEBU[0038] [network] Checking KubeAPI port [6443] on host: 172.27.116.67
DEBU[0038] [network] Checking KubeAPI port [6443] on host: 172.27.116.68
INFO[0038] [network] Removing port listener containers
DEBU[0038] [remove/rke-etcd-port-listener] Checking if container is running on host [172.27.116.66]
DEBU[0038] [remove/rke-etcd-port-listener] Checking if container is running on host [172.27.116.68]
DEBU[0038] [remove/rke-etcd-port-listener] Checking if container is running on host [172.27.116.67]
DEBU[0038] [remove/rke-etcd-port-listener] Checking if container is running on host [172.27.116.65]
DEBU[0038] [remove/rke-etcd-port-listener] Removing container on host [172.27.116.67]
INFO[0038] Removing container [rke-etcd-port-listener] on host [172.27.116.67], try #1
DEBU[0038] [remove/rke-etcd-port-listener] Removing container on host [172.27.116.66]
INFO[0038] Removing container [rke-etcd-port-listener] on host [172.27.116.66], try #1
DEBU[0038] [remove/rke-etcd-port-listener] Removing container on host [172.27.116.65]
INFO[0038] Removing container [rke-etcd-port-listener] on host [172.27.116.65], try #1
DEBU[0038] [remove/rke-etcd-port-listener] Removing container on host [172.27.116.68]
INFO[0038] Removing container [rke-etcd-port-listener] on host [172.27.116.68], try #1
INFO[0038] [remove/rke-etcd-port-listener] Successfully removed container on host [172.27.116.67]
INFO[0039] [remove/rke-etcd-port-listener] Successfully removed container on host [172.27.116.65]
INFO[0039] [remove/rke-etcd-port-listener] Successfully removed container on host [172.27.116.66]
INFO[0039] [remove/rke-etcd-port-listener] Successfully removed container on host [172.27.116.68]
DEBU[0039] [remove/rke-cp-port-listener] Checking if container is running on host [172.27.116.65]
DEBU[0039] [remove/rke-cp-port-listener] Checking if container is running on host [172.27.116.67]
DEBU[0039] [remove/rke-cp-port-listener] Checking if container is running on host [172.27.116.66]
DEBU[0039] [remove/rke-cp-port-listener] Checking if container is running on host [172.27.116.68]
DEBU[0039] [remove/rke-cp-port-listener] Removing container on host [172.27.116.65]
INFO[0039] Removing container [rke-cp-port-listener] on host [172.27.116.65], try #1
DEBU[0039] [remove/rke-cp-port-listener] Removing container on host [172.27.116.68]
INFO[0039] Removing container [rke-cp-port-listener] on host [172.27.116.68], try #1
DEBU[0039] [remove/rke-cp-port-listener] Removing container on host [172.27.116.66]
INFO[0039] Removing container [rke-cp-port-listener] on host [172.27.116.66], try #1
DEBU[0039] [remove/rke-cp-port-listener] Removing container on host [172.27.116.67]
INFO[0039] Removing container [rke-cp-port-listener] on host [172.27.116.67], try #1
INFO[0040] [remove/rke-cp-port-listener] Successfully removed container on host [172.27.116.67]
INFO[0040] [remove/rke-cp-port-listener] Successfully removed container on host [172.27.116.65]
INFO[0040] [remove/rke-cp-port-listener] Successfully removed container on host [172.27.116.68]
INFO[0040] [remove/rke-cp-port-listener] Successfully removed container on host [172.27.116.66]
DEBU[0040] [remove/rke-worker-port-listener] Checking if container is running on host [172.27.116.65]
DEBU[0040] [remove/rke-worker-port-listener] Checking if container is running on host [172.27.116.67]
DEBU[0040] [remove/rke-worker-port-listener] Checking if container is running on host [172.27.116.68]
DEBU[0040] [remove/rke-worker-port-listener] Checking if container is running on host [172.27.116.66]
DEBU[0040] [remove/rke-worker-port-listener] Removing container on host [172.27.116.65]
INFO[0040] Removing container [rke-worker-port-listener] on host [172.27.116.65], try #1
DEBU[0040] [remove/rke-worker-port-listener] Removing container on host [172.27.116.68]
INFO[0040] Removing container [rke-worker-port-listener] on host [172.27.116.68], try #1
DEBU[0040] [remove/rke-worker-port-listener] Removing container on host [172.27.116.67]
INFO[0040] Removing container [rke-worker-port-listener] on host [172.27.116.67], try #1
DEBU[0040] [remove/rke-worker-port-listener] Removing container on host [172.27.116.66]
INFO[0040] Removing container [rke-worker-port-listener] on host [172.27.116.66], try #1
INFO[0040] [remove/rke-worker-port-listener] Successfully removed container on host [172.27.116.68]
INFO[0041] [remove/rke-worker-port-listener] Successfully removed container on host [172.27.116.67]
INFO[0041] [remove/rke-worker-port-listener] Successfully removed container on host [172.27.116.66]
INFO[0041] [remove/rke-worker-port-listener] Successfully removed container on host [172.27.116.65]
INFO[0041] [network] Port listener containers removed successfully
DEBU[0041] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0041] [certificates] kube-apiserver certificate changed, force deploying certs
INFO[0041] [certificates] Deploying kubernetes certificates to Cluster nodes
INFO[0041] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
INFO[0041] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0041] Checking if container [cert-deployer] is running on host [172.27.116.67], try #1
INFO[0041] Checking if container [cert-deployer] is running on host [172.27.116.68], try #1
DEBU[0041] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0041] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
DEBU[0041] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0041] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67], try #1
DEBU[0041] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.68], try #1
INFO[0041] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67]
DEBU[0041] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0041] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.68]
DEBU[0041] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0041] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0041] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
DEBU[0041] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0042] Starting container [cert-deployer] on host [172.27.116.67], try #1
INFO[0042] Starting container [cert-deployer] on host [172.27.116.65], try #1
INFO[0043] Starting container [cert-deployer] on host [172.27.116.66], try #1
INFO[0044] Starting container [cert-deployer] on host [172.27.116.68], try #1
DEBU[0044] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0044] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
DEBU[0044] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0044] Checking if container [cert-deployer] is running on host [172.27.116.67], try #1
DEBU[0045] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0045] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
DEBU[0046] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0046] Checking if container [cert-deployer] is running on host [172.27.116.68], try #1
INFO[0049] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0049] Removing container [cert-deployer] on host [172.27.116.65], try #1
INFO[0049] Checking if container [cert-deployer] is running on host [172.27.116.67], try #1
INFO[0049] Removing container [cert-deployer] on host [172.27.116.67], try #1
INFO[0050] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
INFO[0050] Removing container [cert-deployer] on host [172.27.116.66], try #1
INFO[0051] Checking if container [cert-deployer] is running on host [172.27.116.68], try #1
INFO[0051] Removing container [cert-deployer] on host [172.27.116.68], try #1
INFO[0052] [reconcile] Rebuilding and updating local kube config
DEBU[0052] [reconcile] Rebuilding and updating local kube config, creating new kubeconfig
DEBU[0052] Deploying admin Kubeconfig locally at [./kube_config_cluster.yml]
INFO[0052] Successfully Deployed local admin kubeconfig at [./kube_config_cluster.yml]
DEBU[0052] [version] Using ./kube_config_cluster.yml to connect to Kubernetes cluster..
DEBU[0052] [version] Getting Kubernetes server version..
INFO[0052] [reconcile] host [172.27.116.65] is a control plane node with reachable Kubernetes API endpoint in the cluster
INFO[0052] [certificates] Successfully deployed kubernetes certificates to Cluster nodes
INFO[0052] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.65]
DEBU[0052] [remove/file-deployer] Checking if container is running on host [172.27.116.65]
DEBU[0052] [remove/file-deployer] Container doesn't exist on host [172.27.116.65]
DEBU[0052] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0052] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0052] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0053] Starting container [file-deployer] on host [172.27.116.65], try #1
INFO[0056] Successfully started [file-deployer] container on host [172.27.116.65]
INFO[0056] Waiting for [file-deployer] container to exit on host [172.27.116.65]
INFO[0056] Waiting for [file-deployer] container to exit on host [172.27.116.65]
DEBU[0058] Exit code for [file-deployer] container on host [172.27.116.65] is [0]
DEBU[0058] [remove/file-deployer] Checking if container is running on host [172.27.116.65]
DEBU[0058] [remove/file-deployer] Removing container on host [172.27.116.65]
INFO[0058] Removing container [file-deployer] on host [172.27.116.65], try #1
INFO[0059] [remove/file-deployer] Successfully removed container on host [172.27.116.65]
DEBU[0059] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.65]
INFO[0059] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.66]
DEBU[0059] [remove/file-deployer] Checking if container is running on host [172.27.116.66]
DEBU[0059] [remove/file-deployer] Container doesn't exist on host [172.27.116.66]
DEBU[0059] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0059] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0059] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0060] Starting container [file-deployer] on host [172.27.116.66], try #1
INFO[0062] Successfully started [file-deployer] container on host [172.27.116.66]
INFO[0062] Waiting for [file-deployer] container to exit on host [172.27.116.66]
INFO[0062] Waiting for [file-deployer] container to exit on host [172.27.116.66]
DEBU[0064] Exit code for [file-deployer] container on host [172.27.116.66] is [0]
DEBU[0064] [remove/file-deployer] Checking if container is running on host [172.27.116.66]
DEBU[0064] [remove/file-deployer] Removing container on host [172.27.116.66]
INFO[0064] Removing container [file-deployer] on host [172.27.116.66], try #1
INFO[0065] [remove/file-deployer] Successfully removed container on host [172.27.116.66]
DEBU[0065] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.66]
INFO[0065] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.67]
DEBU[0065] [remove/file-deployer] Checking if container is running on host [172.27.116.67]
DEBU[0065] [remove/file-deployer] Container doesn't exist on host [172.27.116.67]
DEBU[0065] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0065] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0065] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0066] Starting container [file-deployer] on host [172.27.116.67], try #1
INFO[0068] Successfully started [file-deployer] container on host [172.27.116.67]
INFO[0068] Waiting for [file-deployer] container to exit on host [172.27.116.67]
INFO[0068] Waiting for [file-deployer] container to exit on host [172.27.116.67]
DEBU[0070] Exit code for [file-deployer] container on host [172.27.116.67] is [0]
DEBU[0070] [remove/file-deployer] Checking if container is running on host [172.27.116.67]
DEBU[0070] [remove/file-deployer] Removing container on host [172.27.116.67]
INFO[0070] Removing container [file-deployer] on host [172.27.116.67], try #1
INFO[0071] [remove/file-deployer] Successfully removed container on host [172.27.116.67]
DEBU[0071] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.67]
INFO[0071] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.68]
DEBU[0071] [remove/file-deployer] Checking if container is running on host [172.27.116.68]
DEBU[0071] [remove/file-deployer] Container doesn't exist on host [172.27.116.68]
DEBU[0071] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0071] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0071] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0072] Starting container [file-deployer] on host [172.27.116.68], try #1
INFO[0074] Successfully started [file-deployer] container on host [172.27.116.68]
INFO[0074] Waiting for [file-deployer] container to exit on host [172.27.116.68]
INFO[0074] Waiting for [file-deployer] container to exit on host [172.27.116.68]
DEBU[0075] Exit code for [file-deployer] container on host [172.27.116.68] is [0]
DEBU[0075] [remove/file-deployer] Checking if container is running on host [172.27.116.68]
DEBU[0075] [remove/file-deployer] Removing container on host [172.27.116.68]
INFO[0075] Removing container [file-deployer] on host [172.27.116.68], try #1
INFO[0076] [remove/file-deployer] Successfully removed container on host [172.27.116.68]
DEBU[0076] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.68]
INFO[0076] [/etc/kubernetes/audit-policy.yaml] Successfully deployed audit policy file to Cluster control nodes
INFO[0076] [reconcile] Reconciling cluster state
INFO[0076] [reconcile] Check etcd hosts to be deleted
DEBU[0076] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0076] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0076] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0076] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0076] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0076] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0076] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0076] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0076] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0076] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0076] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0076] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0076] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0076] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0076] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0076] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0076] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0076] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0076] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0076] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0076] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0076] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0076] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0076] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0076] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0076] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0076] [reconcile] Check etcd hosts to be added
INFO[0076] [add/etcd] Adding member [etcd-ks-9047988] to etcd cluster
INFO[0077] [add/etcd] Successfully Added member [etcd-ks-9047988] to etcd cluster
DEBU[0077] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0077] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0077] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0077] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0077] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0077] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0077] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0077] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0077] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0077] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0077] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0077] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0077] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0077] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0077] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0077] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0077] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0077] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0077] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0077] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0077] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0077] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0077] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0077] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0077] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0077] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0077] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0078] Starting container [etcd-fix-perm] on host [172.27.116.68], try #1
INFO[0081] Successfully started [etcd-fix-perm] container on host [172.27.116.68]
INFO[0081] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.68]
INFO[0081] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.68]
DEBU[0082] Exit code for [etcd-fix-perm] container on host [172.27.116.68] is [0]
DEBU[0082] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.68]
DEBU[0082] [remove/etcd-fix-perm] Removing container on host [172.27.116.68]
INFO[0082] Removing container [etcd-fix-perm] on host [172.27.116.68], try #1
INFO[0083] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.68]
DEBU[0083] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.68], try #1
DEBU[0083] Image [rancher/mirrored-coreos-etcd:v3.5.0] does not exist on host [172.27.116.68]: Error: No such image: rancher/mirrored-coreos-etcd:v3.5.0
INFO[0083] Pulling image [rancher/mirrored-coreos-etcd:v3.5.0] on host [172.27.116.68], try #1
DEBU[0102] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.68], try #1
INFO[0102] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.68]
INFO[0103] Starting container [etcd] on host [172.27.116.68], try #1
INFO[0106] [etcd] Successfully started [etcd] container on host [172.27.116.68]
DEBU[0106] [etcd] Creating log link for Container [etcd] on host [172.27.116.68]
DEBU[0106] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0106] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.68]
DEBU[0106] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0106] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0109] Starting container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0111] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.68]
DEBU[0111] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0114] [remove/rke-log-linker] Removing container on host [172.27.116.68]
INFO[0114] Removing container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0115] [remove/rke-log-linker] Successfully removed container on host [172.27.116.68]
DEBU[0115] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.68]
DEBU[0125] [etcd] check etcd cluster health on host [172.27.116.65]
INFO[0125] [etcd] etcd host [172.27.116.65] reported healthy=true
DEBU[0125] [reconcile] Check worker hosts to be deleted
DEBU[0125] [reconcile] Check Control plane hosts to be deleted
INFO[0125] [reconcile] Rebuilding and updating local kube config
DEBU[0125] [reconcile] Rebuilding and updating local kube config, creating new kubeconfig
DEBU[0125] Deploying admin Kubeconfig locally at [./kube_config_cluster.yml]
INFO[0125] Successfully Deployed local admin kubeconfig at [./kube_config_cluster.yml]
DEBU[0125] [version] Using ./kube_config_cluster.yml to connect to Kubernetes cluster..
DEBU[0125] [version] Getting Kubernetes server version..
INFO[0125] [reconcile] host [172.27.116.65] is a control plane node with reachable Kubernetes API endpoint in the cluster
DEBU[0125] [restart/kube-apiserver] Checking if container is running on host [172.27.116.66]
DEBU[0125] [restart/kube-apiserver] Restarting container on host [172.27.116.66]
INFO[0125] Restarting container [kube-apiserver] on host [172.27.116.66], try #1
INFO[0135] [restart/kube-apiserver] Successfully restarted container on host [172.27.116.66]
DEBU[0135] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.66]
DEBU[0135] [restart/kube-controller-manager] Restarting container on host [172.27.116.66]
INFO[0135] Restarting container [kube-controller-manager] on host [172.27.116.66], try #1
INFO[0139] [restart/kube-controller-manager] Successfully restarted container on host [172.27.116.66]
DEBU[0139] [restart/kube-apiserver] Checking if container is running on host [172.27.116.67]
DEBU[0139] [restart/kube-apiserver] Restarting container on host [172.27.116.67]
INFO[0139] Restarting container [kube-apiserver] on host [172.27.116.67], try #1
INFO[0148] [restart/kube-apiserver] Successfully restarted container on host [172.27.116.67]
DEBU[0148] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.67]
DEBU[0148] [restart/kube-controller-manager] Restarting container on host [172.27.116.67]
INFO[0148] Restarting container [kube-controller-manager] on host [172.27.116.67], try #1
INFO[0151] [restart/kube-controller-manager] Successfully restarted container on host [172.27.116.67]
DEBU[0151] [restart/kube-apiserver] Checking if container is running on host [172.27.116.68]
DEBU[0151] [restart/kube-apiserver] Container doesn't exist on host [172.27.116.68]
DEBU[0151] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.68]
DEBU[0151] [restart/kube-controller-manager] Container doesn't exist on host [172.27.116.68]
DEBU[0151] [restart/kube-apiserver] Checking if container is running on host [172.27.116.65]
DEBU[0151] [restart/kube-apiserver] Restarting container on host [172.27.116.65]
INFO[0151] Restarting container [kube-apiserver] on host [172.27.116.65], try #1
INFO[0159] [restart/kube-apiserver] Successfully restarted container on host [172.27.116.65]
DEBU[0159] [restart/kube-controller-manager] Checking if container is running on host [172.27.116.65]
DEBU[0159] [restart/kube-controller-manager] Restarting container on host [172.27.116.65]
INFO[0159] Restarting container [kube-controller-manager] on host [172.27.116.65], try #1
INFO[0167] [restart/kube-controller-manager] Successfully restarted container on host [172.27.116.65]
DEBU[0167] [restart/etcd] Checking if container is running on host [ks-9047489]
DEBU[0167] [restart/etcd] Restarting container on host [ks-9047489]
INFO[0167] Restarting container [etcd] on host [ks-9047489], try #1
INFO[0172] [restart/etcd] Successfully restarted container on host [ks-9047489]
DEBU[0172] [restart/etcd] Checking if container is running on host [ks-9047366]
DEBU[0172] [restart/etcd] Restarting container on host [ks-9047366]
INFO[0172] Restarting container [etcd] on host [ks-9047366], try #1
INFO[0176] [restart/etcd] Successfully restarted container on host [ks-9047366]
DEBU[0176] [restart/etcd] Checking if container is running on host [ks-9047368]
DEBU[0176] [restart/etcd] Restarting container on host [ks-9047368]
INFO[0176] Restarting container [etcd] on host [ks-9047368], try #1
INFO[0179] [restart/etcd] Successfully restarted container on host [ks-9047368]
DEBU[0179] [restart/etcd] Checking if container is running on host [ks-9047988]
DEBU[0179] [restart/etcd] Restarting container on host [ks-9047988]
INFO[0179] Restarting container [etcd] on host [ks-9047988], try #1
INFO[0184] [restart/etcd] Successfully restarted container on host [ks-9047988]
INFO[0184] [reconcile] Reconciled cluster state successfully
DEBU[0184] Provided value for maxUnavailable: {1 0 10%}
INFO[0184] max_unavailable_worker got rounded down to 0, resetting to 1
DEBU[0184] Parsed value of maxUnavailable: 1
DEBU[0184] Provided value for maxUnavailable: {0 1 }
DEBU[0184] Parsed value of maxUnavailable: 1
INFO[0184] Setting maxUnavailable for worker nodes to: 1
INFO[0184] Setting maxUnavailable for controlplane nodes to: 1
DEBU[0184] Encryption is disabled in both current and new spec; no action is required
INFO[0184] Pre-pulling kubernetes images
DEBU[0184] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65], try #1
DEBU[0184] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66], try #1
DEBU[0184] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.67], try #1
DEBU[0184] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.68], try #1
INFO[0184] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65]
INFO[0184] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.68]
INFO[0184] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.67]
INFO[0184] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66]
INFO[0184] Kubernetes images pulled successfully
DEBU[0184] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0184] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0184] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0184] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0184] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0184] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0184] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0184] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0184] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0184] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0184] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0184] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0184] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0184] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0184] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0184] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0184] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0184] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0184] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0184] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0184] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0184] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0184] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0184] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0184] [etcd] Building up etcd plane..
DEBU[0184] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0184] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0184] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0184] Starting container [etcd-fix-perm] on host [172.27.116.65], try #1
INFO[0186] Successfully started [etcd-fix-perm] container on host [172.27.116.65]
INFO[0186] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.65]
INFO[0186] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.65]
DEBU[0187] Exit code for [etcd-fix-perm] container on host [172.27.116.65] is [0]
DEBU[0187] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.65]
DEBU[0187] [remove/etcd-fix-perm] Removing container on host [172.27.116.65]
INFO[0187] Removing container [etcd-fix-perm] on host [172.27.116.65], try #1
INFO[0188] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.65]
DEBU[0188] [etcd] Container [etcd] is already running on host [172.27.116.65]
DEBU[0188] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.65]
DEBU[0188] slice is not equal, showing data in new value which is not in old value: map[--initial-cluster-state=existing:{} --initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380,etcd-ks-9047988=https://172.27.116.58:2380:{}]
DEBU[0188] slice is not equal, showing data in old value which is not in new value: map[--initial-cluster-state=new:{} --initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380:{}]
DEBU[0188] [etcd] Container [etcd] is eligible for upgrade on host [172.27.116.65]
DEBU[0188] [etcd] Checking for deployed [etcd]
INFO[0188] Checking if container [etcd] is running on host [172.27.116.65], try #1
DEBU[0188] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.65], try #1
INFO[0188] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.65]
DEBU[0188] [etcd] Stopping old container
INFO[0188] Checking if container [old-etcd] is running on host [172.27.116.65], try #1
INFO[0188] Stopping container [etcd] on host [172.27.116.65] with stopTimeoutDuration [5s], try #1
INFO[0191] Waiting for [etcd] container to exit on host [172.27.116.65]
DEBU[0191] Exit code for [etcd] container on host [172.27.116.65] is [0]
INFO[0191] Renaming container [etcd] to [old-etcd] on host [172.27.116.65], try #1
DEBU[0191] [etcd] Successfully stopped old container etcd on host [172.27.116.65]
INFO[0193] Starting container [etcd] on host [172.27.116.65], try #1
INFO[0194] [etcd] Successfully updated [etcd] container on host [172.27.116.65]
DEBU[0194] [etcd] Removing old container
INFO[0194] Removing container [old-etcd] on host [172.27.116.65], try #1
DEBU[0195] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0195] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0195] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0195] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.65]
DEBU[0195] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.55:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0195] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.65]
DEBU[0195] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.65]
INFO[0195] Removing container [etcd-rolling-snapshots] on host [172.27.116.65], try #1
INFO[0199] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.65]
DEBU[0199] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0199] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
INFO[0200] Starting container [etcd-rolling-snapshots] on host [172.27.116.65], try #1
INFO[0203] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.65]
DEBU[0208] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0208] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0208] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
INFO[0209] Starting container [rke-bundle-cert] on host [172.27.116.65], try #1
INFO[0211] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.65]
INFO[0211] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.65]
DEBU[0212] Exit code for [rke-bundle-cert] container on host [172.27.116.65] is [0]
INFO[0212] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.65]
INFO[0212] Removing container [rke-bundle-cert] on host [172.27.116.65], try #1
DEBU[0213] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0213] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0213] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0213] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0213] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0214] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0216] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0216] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0217] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0217] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0217] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0217] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.65]
DEBU[0217] [etcd] Creating log link for Container [etcd] on host [172.27.116.65]
DEBU[0217] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0217] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0217] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0217] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0218] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0219] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0219] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0220] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0220] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0221] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0221] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.65]
DEBU[0221] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0221] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0221] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0221] Starting container [etcd-fix-perm] on host [172.27.116.66], try #1
INFO[0223] Successfully started [etcd-fix-perm] container on host [172.27.116.66]
INFO[0223] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.66]
INFO[0223] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.66]
DEBU[0224] Exit code for [etcd-fix-perm] container on host [172.27.116.66] is [0]
DEBU[0224] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.66]
DEBU[0224] [remove/etcd-fix-perm] Removing container on host [172.27.116.66]
INFO[0224] Removing container [etcd-fix-perm] on host [172.27.116.66], try #1
INFO[0225] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.66]
DEBU[0225] [etcd] Container [etcd] is already running on host [172.27.116.66]
DEBU[0225] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.66]
DEBU[0225] slice is not equal, showing data in new value which is not in old value: map[--initial-cluster-state=existing:{} --initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380,etcd-ks-9047988=https://172.27.116.58:2380:{}]
DEBU[0225] slice is not equal, showing data in old value which is not in new value: map[--initial-cluster-state=new:{} --initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380:{}]
DEBU[0225] [etcd] Container [etcd] is eligible for upgrade on host [172.27.116.66]
DEBU[0225] [etcd] Checking for deployed [etcd]
INFO[0225] Checking if container [etcd] is running on host [172.27.116.66], try #1
DEBU[0225] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.66], try #1
INFO[0225] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.66]
DEBU[0225] [etcd] Stopping old container
INFO[0225] Checking if container [old-etcd] is running on host [172.27.116.66], try #1
INFO[0225] Stopping container [etcd] on host [172.27.116.66] with stopTimeoutDuration [5s], try #1
INFO[0228] Waiting for [etcd] container to exit on host [172.27.116.66]
DEBU[0228] Exit code for [etcd] container on host [172.27.116.66] is [0]
INFO[0228] Renaming container [etcd] to [old-etcd] on host [172.27.116.66], try #1
DEBU[0228] [etcd] Successfully stopped old container etcd on host [172.27.116.66]
INFO[0228] Starting container [etcd] on host [172.27.116.66], try #1
INFO[0230] [etcd] Successfully updated [etcd] container on host [172.27.116.66]
DEBU[0230] [etcd] Removing old container
INFO[0230] Removing container [old-etcd] on host [172.27.116.66], try #1
DEBU[0230] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0230] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0230] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0230] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.66]
DEBU[0230] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.56:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0230] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.66]
DEBU[0230] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.66]
INFO[0230] Removing container [etcd-rolling-snapshots] on host [172.27.116.66], try #1
INFO[0232] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.66]
DEBU[0232] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0232] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
INFO[0233] Starting container [etcd-rolling-snapshots] on host [172.27.116.66], try #1
INFO[0235] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.66]
DEBU[0240] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0240] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0240] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
INFO[0240] Starting container [rke-bundle-cert] on host [172.27.116.66], try #1
INFO[0242] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.66]
INFO[0242] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.66]
DEBU[0243] Exit code for [rke-bundle-cert] container on host [172.27.116.66] is [0]
INFO[0243] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.66]
INFO[0243] Removing container [rke-bundle-cert] on host [172.27.116.66], try #1
DEBU[0243] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0243] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0243] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0243] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0243] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0244] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0246] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0246] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0247] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0247] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0247] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0247] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.66]
DEBU[0247] [etcd] Creating log link for Container [etcd] on host [172.27.116.66]
DEBU[0247] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0247] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0247] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0247] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0248] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0250] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0250] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0251] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0251] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0252] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0252] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.66]
DEBU[0252] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0252] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0252] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0252] Starting container [etcd-fix-perm] on host [172.27.116.67], try #1
INFO[0254] Successfully started [etcd-fix-perm] container on host [172.27.116.67]
INFO[0254] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.67]
INFO[0254] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.67]
DEBU[0255] Exit code for [etcd-fix-perm] container on host [172.27.116.67] is [0]
DEBU[0255] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.67]
DEBU[0255] [remove/etcd-fix-perm] Removing container on host [172.27.116.67]
INFO[0255] Removing container [etcd-fix-perm] on host [172.27.116.67], try #1
INFO[0256] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.67]
DEBU[0256] [etcd] Container [etcd] is already running on host [172.27.116.67]
DEBU[0256] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.67]
DEBU[0256] slice is not equal, showing data in new value which is not in old value: map[--initial-cluster-state=existing:{} --initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380,etcd-ks-9047988=https://172.27.116.58:2380:{}]
DEBU[0256] slice is not equal, showing data in old value which is not in new value: map[--initial-cluster-state=new:{} --initial-cluster=etcd-ks-9047489=https://172.27.116.55:2380,etcd-ks-9047366=https://172.27.116.56:2380,etcd-ks-9047368=https://172.27.116.57:2380:{}]
DEBU[0256] [etcd] Container [etcd] is eligible for upgrade on host [172.27.116.67]
DEBU[0256] [etcd] Checking for deployed [etcd]
INFO[0256] Checking if container [etcd] is running on host [172.27.116.67], try #1
DEBU[0256] Checking if image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.67], try #1
INFO[0256] Image [rancher/mirrored-coreos-etcd:v3.5.0] exists on host [172.27.116.67]
DEBU[0256] [etcd] Stopping old container
INFO[0256] Checking if container [old-etcd] is running on host [172.27.116.67], try #1
INFO[0256] Stopping container [etcd] on host [172.27.116.67] with stopTimeoutDuration [5s], try #1
INFO[0258] Waiting for [etcd] container to exit on host [172.27.116.67]
DEBU[0258] Exit code for [etcd] container on host [172.27.116.67] is [0]
INFO[0258] Renaming container [etcd] to [old-etcd] on host [172.27.116.67], try #1
DEBU[0258] [etcd] Successfully stopped old container etcd on host [172.27.116.67]
INFO[0259] Starting container [etcd] on host [172.27.116.67], try #1
INFO[0260] [etcd] Successfully updated [etcd] container on host [172.27.116.67]
DEBU[0260] [etcd] Removing old container
INFO[0260] Removing container [old-etcd] on host [172.27.116.67], try #1
DEBU[0260] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0260] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0260] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0260] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.67]
DEBU[0260] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.57:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.67]
DEBU[0260] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.67]
DEBU[0260] [remove/etcd-rolling-snapshots] Removing container on host [172.27.116.67]
INFO[0260] Removing container [etcd-rolling-snapshots] on host [172.27.116.67], try #1
INFO[0262] [remove/etcd-rolling-snapshots] Successfully removed container on host [172.27.116.67]
DEBU[0262] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67], try #1
INFO[0262] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67]
INFO[0264] Starting container [etcd-rolling-snapshots] on host [172.27.116.67], try #1
INFO[0265] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.67]
DEBU[0270] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0270] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67], try #1
INFO[0270] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67]
INFO[0271] Starting container [rke-bundle-cert] on host [172.27.116.67], try #1
INFO[0273] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.67]
INFO[0273] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.67]
DEBU[0274] Exit code for [rke-bundle-cert] container on host [172.27.116.67] is [0]
INFO[0274] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.67]
INFO[0274] Removing container [rke-bundle-cert] on host [172.27.116.67], try #1
DEBU[0274] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.67]
DEBU[0274] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0274] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.67]
DEBU[0274] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0274] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0275] Starting container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0277] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.67]
DEBU[0277] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0278] [remove/rke-log-linker] Removing container on host [172.27.116.67]
INFO[0278] Removing container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0279] [remove/rke-log-linker] Successfully removed container on host [172.27.116.67]
DEBU[0279] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.67]
DEBU[0279] [etcd] Creating log link for Container [etcd] on host [172.27.116.67]
DEBU[0279] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0279] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.67]
DEBU[0279] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0279] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0280] Starting container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0282] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.67]
DEBU[0282] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0283] [remove/rke-log-linker] Removing container on host [172.27.116.67]
INFO[0283] Removing container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0284] [remove/rke-log-linker] Successfully removed container on host [172.27.116.67]
DEBU[0284] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.67]
DEBU[0284] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0284] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0284] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0286] Starting container [etcd-fix-perm] on host [172.27.116.68], try #1
INFO[0288] Successfully started [etcd-fix-perm] container on host [172.27.116.68]
INFO[0288] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.68]
INFO[0288] Waiting for [etcd-fix-perm] container to exit on host [172.27.116.68]
DEBU[0290] Exit code for [etcd-fix-perm] container on host [172.27.116.68] is [0]
DEBU[0290] [remove/etcd-fix-perm] Checking if container is running on host [172.27.116.68]
DEBU[0290] [remove/etcd-fix-perm] Removing container on host [172.27.116.68]
INFO[0290] Removing container [etcd-fix-perm] on host [172.27.116.68], try #1
INFO[0290] [remove/etcd-fix-perm] Successfully removed container on host [172.27.116.68]
DEBU[0290] [etcd] Container [etcd] is already running on host [172.27.116.68]
DEBU[0290] [etcd] Checking if container [etcd] is eligible for upgrade on host [172.27.116.68]
DEBU[0290] [etcd] Container [etcd] is not eligible for upgrade on host [172.27.116.68]
DEBU[0290] Extracted version [v0.1.78] from image [rancher/rke-tools:v0.1.78]
DEBU[0290] Extracted version [v0.1.80] from image [rancher/rke-tools:v0.1.80]
DEBU[0290] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0290] [etcd] Running rolling snapshot container [etcd-snapshot-once] on host [172.27.116.68]
DEBU[0290] [etcd] Using command [/opt/rke-tools/rke-etcd-backup etcd-backup save --cacert /etc/kubernetes/ssl/kube-ca.pem --cert /etc/kubernetes/ssl/kube-node.pem --key /etc/kubernetes/ssl/kube-node-key.pem --name etcd-rolling-snapshots --endpoints=172.27.116.58:2379 --creation=6h --retention=360h] for rolling snapshot container [etcd-rolling-snapshots] on host [172.27.116.68]
DEBU[0290] [remove/etcd-rolling-snapshots] Checking if container is running on host [172.27.116.68]
DEBU[0290] [remove/etcd-rolling-snapshots] Container doesn't exist on host [172.27.116.68]
DEBU[0290] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.68], try #1
INFO[0290] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.68]
INFO[0291] Starting container [etcd-rolling-snapshots] on host [172.27.116.68], try #1
INFO[0293] [etcd] Successfully started [etcd-rolling-snapshots] container on host [172.27.116.68]
DEBU[0298] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0298] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.68], try #1
INFO[0298] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.68]
INFO[0299] Starting container [rke-bundle-cert] on host [172.27.116.68], try #1
INFO[0300] [certificates] Successfully started [rke-bundle-cert] container on host [172.27.116.68]
INFO[0300] Waiting for [rke-bundle-cert] container to exit on host [172.27.116.68]
DEBU[0302] Exit code for [rke-bundle-cert] container on host [172.27.116.68] is [0]
INFO[0302] [certificates] successfully saved certificate bundle [/opt/rke/etcd-snapshots//pki.bundle.tar.gz] on host [172.27.116.68]
INFO[0302] Removing container [rke-bundle-cert] on host [172.27.116.68], try #1
DEBU[0302] [etcd] Creating log link for Container [etcd-rolling-snapshots] on host [172.27.116.68]
DEBU[0302] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0302] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.68]
DEBU[0302] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0302] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0304] Starting container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0306] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.68]
DEBU[0306] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0307] [remove/rke-log-linker] Removing container on host [172.27.116.68]
INFO[0307] Removing container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0308] [remove/rke-log-linker] Successfully removed container on host [172.27.116.68]
DEBU[0308] [etcd] Successfully created log link for Container [etcd-rolling-snapshots] on host [172.27.116.68]
DEBU[0308] [etcd] Creating log link for Container [etcd] on host [172.27.116.68]
DEBU[0308] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0308] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.68]
DEBU[0308] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0308] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0309] Starting container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0311] [etcd] Successfully started [rke-log-linker] container on host [172.27.116.68]
DEBU[0311] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0313] [remove/rke-log-linker] Removing container on host [172.27.116.68]
INFO[0313] Removing container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0314] [remove/rke-log-linker] Successfully removed container on host [172.27.116.68]
DEBU[0314] [etcd] Successfully created log link for Container [etcd] on host [172.27.116.68]
INFO[0314] [etcd] Successfully started etcd plane.. Checking etcd cluster health
DEBU[0314] [etcd] check etcd cluster health on host [172.27.116.65]
INFO[0314] [etcd] etcd host [172.27.116.65] reported healthy=true
DEBU[0314] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0314] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0314] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0314] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0314] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0314] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0314] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0314] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0314] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0314] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0314] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0314] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0314] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0314] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0314] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0314] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0314] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0314] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0314] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0314] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0314] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0314] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0314] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0314] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0314] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0314] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0314] [controlplane] Now checking status of node ks-9047489, try #1
DEBU[0314] Checking node list for node [ks-9047489], try #1
DEBU[0314] [controlplane] Found node by name ks-9047489
INFO[0314] [controlplane] Now checking status of node ks-9047366, try #1
DEBU[0314] Checking node list for node [ks-9047366], try #1
DEBU[0314] [controlplane] Found node by name ks-9047366
INFO[0314] [controlplane] Now checking status of node ks-9047368, try #1
DEBU[0314] Checking node list for node [ks-9047368], try #1
DEBU[0314] [controlplane] Found node by name ks-9047368
INFO[0314] [controlplane] Now checking status of node ks-9047988, try #1
DEBU[0314] Checking node list for node [ks-9047988], try #1
DEBU[0314] [controlplane] Found node by name ks-9047988
INFO[0314] [controlplane] Processing controlplane hosts for upgrade 1 at a time
INFO[0314] Processing controlplane host ks-9047489
INFO[0314] [controlplane] Now checking status of node ks-9047489, try #1
DEBU[0314] Checking node list for node [ks-9047489], try #1
DEBU[0314] [controlplane] Found node by name ks-9047489
INFO[0314] [controlplane] Getting list of nodes for upgrade
DEBU[0314] [controlplane] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.65]
DEBU[0314] [controlplane] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.65]
DEBU[0314] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.65]
DEBU[0314] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.57:2379,https://172.27.116.58:2379:{}]
DEBU[0314] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.57:2379:{}]
DEBU[0314] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.65]
DEBU[0314] [controlplane] Host ks-9047489 is upgradable because kube-apiserver has changed
DEBU[0314] [worker] Checking if container [nginx-proxy] is eligible for upgrade on host [172.27.116.65]
DEBU[0314] [worker] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.65]
DEBU[0314] [worker] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.65]
DEBU[0314] [worker] Checking if container [kubelet] is eligible for upgrade on host [172.27.116.65]
DEBU[0314] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0314] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0314] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0314] [worker] Container [kubelet] is not eligible for upgrade on host [172.27.116.65]
DEBU[0314] [worker] Checking if container [kube-proxy] is eligible for upgrade on host [172.27.116.65]
DEBU[0314] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0314] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0314] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0314] [worker] Container [kube-proxy] is not eligible for upgrade on host [172.27.116.65]
DEBU[0314] [worker] Host ks-9047489 is not upgradable
DEBU[0314] [controlplane] Cordoning node ks-9047489
DEBU[0314] Checking node list for node [ks-9047489], try #1
DEBU[0315] Checking node list for node [ks-9047489], try #1
DEBU[0315] Node ks-9047489 is already cordoned: true
INFO[0315] Upgrading controlplane components for control host ks-9047489
DEBU[0315] [remove/nginx-proxy] Checking if container is running on host [172.27.116.65]
DEBU[0315] [remove/nginx-proxy] Container doesn't exist on host [172.27.116.65]
INFO[0315] Checking if container [service-sidekick] is running on host [172.27.116.65], try #1
DEBU[0315] [sidekick] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.65]
DEBU[0315] [sidekick] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.65]
INFO[0315] [sidekick] Sidekick container already created on host [172.27.116.65]
DEBU[0315] [controlplane] Container [kube-apiserver] is already running on host [172.27.116.65]
DEBU[0315] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.65]
DEBU[0315] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.57:2379,https://172.27.116.58:2379:{}]
DEBU[0315] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.57:2379:{}]
DEBU[0315] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.65]
DEBU[0315] [controlplane] Checking for deployed [kube-apiserver]
INFO[0315] Checking if container [kube-apiserver] is running on host [172.27.116.65], try #1
DEBU[0315] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65], try #1
INFO[0315] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.65]
DEBU[0315] [controlplane] Stopping old container
INFO[0315] Checking if container [old-kube-apiserver] is running on host [172.27.116.65], try #1
INFO[0315] Stopping container [kube-apiserver] on host [172.27.116.65] with stopTimeoutDuration [5s], try #1
INFO[0321] Waiting for [kube-apiserver] container to exit on host [172.27.116.65]
DEBU[0321] Exit code for [kube-apiserver] container on host [172.27.116.65] is [137]
INFO[0321] Renaming container [kube-apiserver] to [old-kube-apiserver] on host [172.27.116.65], try #1
DEBU[0321] [controlplane] Successfully stopped old container kube-apiserver on host [172.27.116.65]
INFO[0322] Starting container [kube-apiserver] on host [172.27.116.65], try #1
INFO[0323] [controlplane] Successfully updated [kube-apiserver] container on host [172.27.116.65]
DEBU[0323] [controlplane] Removing old container
INFO[0323] Removing container [old-kube-apiserver] on host [172.27.116.65], try #1
INFO[0328] [healthcheck] Start Healthcheck on service [kube-apiserver] on host [172.27.116.65]
DEBU[0328] [healthcheck] Service [kube-apiserver] is not healthy on host [172.27.116.65]. Response code: [500], response body: [+]ping ok
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
INFO[0333] [healthcheck] service [kube-apiserver] on host [172.27.116.65] is healthy
DEBU[0333] [controlplane] Creating log link for Container [kube-apiserver] on host [172.27.116.65]
DEBU[0333] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0333] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0333] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0333] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0334] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0336] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0336] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0337] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0337] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0337] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0337] [controlplane] Successfully created log link for Container [kube-apiserver] on host [172.27.116.65]
DEBU[0337] [controlplane] Container [kube-controller-manager] is already running on host [172.27.116.65]
DEBU[0337] [controlplane] Checking if container [kube-controller-manager] is eligible for upgrade on host [172.27.116.65]
DEBU[0337] [controlplane] Container [kube-controller-manager] is not eligible for upgrade on host [172.27.116.65]
INFO[0337] [healthcheck] Start Healthcheck on service [kube-controller-manager] on host [172.27.116.65]
INFO[0337] [healthcheck] service [kube-controller-manager] on host [172.27.116.65] is healthy
DEBU[0337] [controlplane] Creating log link for Container [kube-controller-manager] on host [172.27.116.65]
DEBU[0337] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0337] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0337] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0337] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0338] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0339] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0339] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0340] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0340] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0341] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0341] [controlplane] Successfully created log link for Container [kube-controller-manager] on host [172.27.116.65]
DEBU[0341] [controlplane] Container [kube-scheduler] is already running on host [172.27.116.65]
DEBU[0341] [controlplane] Checking if container [kube-scheduler] is eligible for upgrade on host [172.27.116.65]
DEBU[0341] [controlplane] Container [kube-scheduler] is not eligible for upgrade on host [172.27.116.65]
INFO[0341] [healthcheck] Start Healthcheck on service [kube-scheduler] on host [172.27.116.65]
INFO[0341] [healthcheck] service [kube-scheduler] on host [172.27.116.65] is healthy
DEBU[0341] [controlplane] Creating log link for Container [kube-scheduler] on host [172.27.116.65]
DEBU[0341] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0341] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.65]
DEBU[0341] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0341] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0342] Starting container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0344] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.65]
DEBU[0344] [remove/rke-log-linker] Checking if container is running on host [172.27.116.65]
DEBU[0345] [remove/rke-log-linker] Removing container on host [172.27.116.65]
INFO[0345] Removing container [rke-log-linker] on host [172.27.116.65], try #1
INFO[0346] [remove/rke-log-linker] Successfully removed container on host [172.27.116.65]
DEBU[0346] [controlplane] Successfully created log link for Container [kube-scheduler] on host [172.27.116.65]
INFO[0346] [controlplane] Now checking status of node ks-9047489, try #1
DEBU[0346] Checking node list for node [ks-9047489], try #1
DEBU[0346] [controlplane] Found node by name ks-9047489
DEBU[0346] Checking node list for node [ks-9047489], try #1
DEBU[0346] Checking node list for node [ks-9047489], try #1
DEBU[0346] Node ks-9047489 is already cordoned: false
INFO[0346] Processing controlplane host ks-9047366
INFO[0346] [controlplane] Now checking status of node ks-9047366, try #1
DEBU[0346] Checking node list for node [ks-9047366], try #1
DEBU[0346] [controlplane] Found node by name ks-9047366
INFO[0346] [controlplane] Getting list of nodes for upgrade
DEBU[0346] [controlplane] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.66]
DEBU[0346] [controlplane] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.66]
DEBU[0346] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.66]
DEBU[0346] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.56:2379,https://172.27.116.55:2379,https://172.27.116.57:2379,https://172.27.116.58:2379:{}]
DEBU[0346] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.56:2379,https://172.27.116.55:2379,https://172.27.116.57:2379:{}]
DEBU[0346] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.66]
DEBU[0346] [controlplane] Host ks-9047366 is upgradable because kube-apiserver has changed
DEBU[0346] [worker] Checking if container [nginx-proxy] is eligible for upgrade on host [172.27.116.66]
DEBU[0346] [worker] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.66]
DEBU[0346] [worker] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.66]
DEBU[0346] [worker] Checking if container [kubelet] is eligible for upgrade on host [172.27.116.66]
DEBU[0346] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0346] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0346] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0346] [worker] Container [kubelet] is not eligible for upgrade on host [172.27.116.66]
DEBU[0346] [worker] Checking if container [kube-proxy] is eligible for upgrade on host [172.27.116.66]
DEBU[0346] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0346] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0346] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0346] [worker] Container [kube-proxy] is not eligible for upgrade on host [172.27.116.66]
DEBU[0346] [worker] Host ks-9047366 is not upgradable
DEBU[0346] [controlplane] Cordoning node ks-9047366
DEBU[0346] Checking node list for node [ks-9047366], try #1
DEBU[0346] Checking node list for node [ks-9047366], try #1
DEBU[0346] Node ks-9047366 is already cordoned: true
INFO[0346] Upgrading controlplane components for control host ks-9047366
DEBU[0346] [remove/nginx-proxy] Checking if container is running on host [172.27.116.66]
DEBU[0346] [remove/nginx-proxy] Container doesn't exist on host [172.27.116.66]
INFO[0346] Checking if container [service-sidekick] is running on host [172.27.116.66], try #1
DEBU[0346] [sidekick] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.66]
DEBU[0346] [sidekick] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.66]
INFO[0346] [sidekick] Sidekick container already created on host [172.27.116.66]
DEBU[0346] [controlplane] Container [kube-apiserver] is already running on host [172.27.116.66]
DEBU[0346] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.66]
DEBU[0346] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.56:2379,https://172.27.116.55:2379,https://172.27.116.57:2379,https://172.27.116.58:2379:{}]
DEBU[0346] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.56:2379,https://172.27.116.55:2379,https://172.27.116.57:2379:{}]
DEBU[0346] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.66]
DEBU[0346] [controlplane] Checking for deployed [kube-apiserver]
INFO[0346] Checking if container [kube-apiserver] is running on host [172.27.116.66], try #1
DEBU[0346] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66], try #1
INFO[0346] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.66]
DEBU[0346] [controlplane] Stopping old container
INFO[0346] Checking if container [old-kube-apiserver] is running on host [172.27.116.66], try #1
INFO[0346] Stopping container [kube-apiserver] on host [172.27.116.66] with stopTimeoutDuration [5s], try #1
INFO[0353] Waiting for [kube-apiserver] container to exit on host [172.27.116.66]
DEBU[0353] Exit code for [kube-apiserver] container on host [172.27.116.66] is [137]
INFO[0353] Renaming container [kube-apiserver] to [old-kube-apiserver] on host [172.27.116.66], try #1
DEBU[0353] [controlplane] Successfully stopped old container kube-apiserver on host [172.27.116.66]
INFO[0355] Starting container [kube-apiserver] on host [172.27.116.66], try #1
INFO[0357] [controlplane] Successfully updated [kube-apiserver] container on host [172.27.116.66]
DEBU[0357] [controlplane] Removing old container
INFO[0357] Removing container [old-kube-apiserver] on host [172.27.116.66], try #1
INFO[0359] [healthcheck] Start Healthcheck on service [kube-apiserver] on host [172.27.116.66]
DEBU[0361] [healthcheck] Service [kube-apiserver] is not healthy on host [172.27.116.66]. Response code: [403], response body: {"kind":"Status","apiVersion":"v1","metadata":{},"status":"Failure","message":"forbidden: User \"kube-apiserver\" cannot get path \"/healthz\"","reason":"Forbidden","details":{},"code":403}
, try #1
INFO[0366] [healthcheck] service [kube-apiserver] on host [172.27.116.66] is healthy
DEBU[0366] [controlplane] Creating log link for Container [kube-apiserver] on host [172.27.116.66]
DEBU[0366] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0366] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0366] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0366] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0367] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0369] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0369] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0371] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0371] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0371] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0371] [controlplane] Successfully created log link for Container [kube-apiserver] on host [172.27.116.66]
DEBU[0371] [controlplane] Container [kube-controller-manager] is already running on host [172.27.116.66]
DEBU[0371] [controlplane] Checking if container [kube-controller-manager] is eligible for upgrade on host [172.27.116.66]
DEBU[0371] [controlplane] Container [kube-controller-manager] is not eligible for upgrade on host [172.27.116.66]
INFO[0371] [healthcheck] Start Healthcheck on service [kube-controller-manager] on host [172.27.116.66]
INFO[0371] [healthcheck] service [kube-controller-manager] on host [172.27.116.66] is healthy
DEBU[0371] [controlplane] Creating log link for Container [kube-controller-manager] on host [172.27.116.66]
DEBU[0371] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0371] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0371] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0371] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0372] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0374] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0374] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0376] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0376] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0376] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0376] [controlplane] Successfully created log link for Container [kube-controller-manager] on host [172.27.116.66]
DEBU[0376] [controlplane] Container [kube-scheduler] is already running on host [172.27.116.66]
DEBU[0376] [controlplane] Checking if container [kube-scheduler] is eligible for upgrade on host [172.27.116.66]
DEBU[0376] [controlplane] Container [kube-scheduler] is not eligible for upgrade on host [172.27.116.66]
INFO[0376] [healthcheck] Start Healthcheck on service [kube-scheduler] on host [172.27.116.66]
INFO[0376] [healthcheck] service [kube-scheduler] on host [172.27.116.66] is healthy
DEBU[0376] [controlplane] Creating log link for Container [kube-scheduler] on host [172.27.116.66]
DEBU[0376] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0376] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.66]
DEBU[0376] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0376] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0377] Starting container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0379] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.66]
DEBU[0379] [remove/rke-log-linker] Checking if container is running on host [172.27.116.66]
DEBU[0380] [remove/rke-log-linker] Removing container on host [172.27.116.66]
INFO[0380] Removing container [rke-log-linker] on host [172.27.116.66], try #1
INFO[0381] [remove/rke-log-linker] Successfully removed container on host [172.27.116.66]
DEBU[0381] [controlplane] Successfully created log link for Container [kube-scheduler] on host [172.27.116.66]
INFO[0381] [controlplane] Now checking status of node ks-9047366, try #1
DEBU[0381] Checking node list for node [ks-9047366], try #1
DEBU[0381] [controlplane] Found node by name ks-9047366
DEBU[0381] Checking node list for node [ks-9047366], try #1
DEBU[0381] Checking node list for node [ks-9047366], try #1
DEBU[0381] Node ks-9047366 is already cordoned: false
INFO[0381] Processing controlplane host ks-9047368
INFO[0381] [controlplane] Now checking status of node ks-9047368, try #1
DEBU[0381] Checking node list for node [ks-9047368], try #1
DEBU[0381] [controlplane] Found node by name ks-9047368
INFO[0381] [controlplane] Getting list of nodes for upgrade
DEBU[0381] [controlplane] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.67]
DEBU[0381] [controlplane] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.67]
DEBU[0381] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.67]
DEBU[0381] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.57:2379,https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.58:2379:{}]
DEBU[0381] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.57:2379,https://172.27.116.55:2379,https://172.27.116.56:2379:{}]
DEBU[0381] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.67]
DEBU[0381] [controlplane] Host ks-9047368 is upgradable because kube-apiserver has changed
DEBU[0381] [worker] Checking if container [nginx-proxy] is eligible for upgrade on host [172.27.116.67]
DEBU[0381] [worker] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.67]
DEBU[0381] [worker] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.67]
DEBU[0381] [worker] Checking if container [kubelet] is eligible for upgrade on host [172.27.116.67]
DEBU[0381] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0381] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0381] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0381] [worker] Container [kubelet] is not eligible for upgrade on host [172.27.116.67]
DEBU[0381] [worker] Checking if container [kube-proxy] is eligible for upgrade on host [172.27.116.67]
DEBU[0381] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0381] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0381] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0381] [worker] Container [kube-proxy] is not eligible for upgrade on host [172.27.116.67]
DEBU[0381] [worker] Host ks-9047368 is not upgradable
DEBU[0381] [controlplane] Cordoning node ks-9047368
DEBU[0381] Checking node list for node [ks-9047368], try #1
DEBU[0381] Checking node list for node [ks-9047368], try #1
DEBU[0381] Node ks-9047368 is already cordoned: true
INFO[0381] Upgrading controlplane components for control host ks-9047368
DEBU[0381] [remove/nginx-proxy] Checking if container is running on host [172.27.116.67]
DEBU[0381] [remove/nginx-proxy] Container doesn't exist on host [172.27.116.67]
INFO[0381] Checking if container [service-sidekick] is running on host [172.27.116.67], try #1
DEBU[0381] [sidekick] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.67]
DEBU[0381] [sidekick] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.67]
INFO[0381] [sidekick] Sidekick container already created on host [172.27.116.67]
DEBU[0381] [controlplane] Container [kube-apiserver] is already running on host [172.27.116.67]
DEBU[0381] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.67]
DEBU[0381] slice is not equal, showing data in new value which is not in old value: map[--etcd-servers=https://172.27.116.57:2379,https://172.27.116.55:2379,https://172.27.116.56:2379,https://172.27.116.58:2379:{}]
DEBU[0381] slice is not equal, showing data in old value which is not in new value: map[--etcd-servers=https://172.27.116.57:2379,https://172.27.116.55:2379,https://172.27.116.56:2379:{}]
DEBU[0381] [controlplane] Container [kube-apiserver] is eligible for upgrade on host [172.27.116.67]
DEBU[0381] [controlplane] Checking for deployed [kube-apiserver]
INFO[0381] Checking if container [kube-apiserver] is running on host [172.27.116.67], try #1
DEBU[0381] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.67], try #1
INFO[0381] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.67]
DEBU[0381] [controlplane] Stopping old container
INFO[0381] Checking if container [old-kube-apiserver] is running on host [172.27.116.67], try #1
INFO[0381] Stopping container [kube-apiserver] on host [172.27.116.67] with stopTimeoutDuration [5s], try #1
INFO[0388] Waiting for [kube-apiserver] container to exit on host [172.27.116.67]
DEBU[0388] Exit code for [kube-apiserver] container on host [172.27.116.67] is [137]
INFO[0388] Renaming container [kube-apiserver] to [old-kube-apiserver] on host [172.27.116.67], try #1
DEBU[0388] [controlplane] Successfully stopped old container kube-apiserver on host [172.27.116.67]
INFO[0389] Starting container [kube-apiserver] on host [172.27.116.67], try #1
INFO[0391] [controlplane] Successfully updated [kube-apiserver] container on host [172.27.116.67]
DEBU[0391] [controlplane] Removing old container
INFO[0391] Removing container [old-kube-apiserver] on host [172.27.116.67], try #1
INFO[0394] [healthcheck] Start Healthcheck on service [kube-apiserver] on host [172.27.116.67]
DEBU[0395] [healthcheck] Service [kube-apiserver] is not healthy on host [172.27.116.67]. Response code: [403], response body: {"kind":"Status","apiVersion":"v1","metadata":{},"status":"Failure","message":"forbidden: User \"kube-apiserver\" cannot get path \"/healthz\"","reason":"Forbidden","details":{},"code":403}
, try #1
INFO[0400] [healthcheck] service [kube-apiserver] on host [172.27.116.67] is healthy
DEBU[0400] [controlplane] Creating log link for Container [kube-apiserver] on host [172.27.116.67]
DEBU[0400] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0400] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.67]
DEBU[0400] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0400] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0401] Starting container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0402] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.67]
DEBU[0402] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0403] [remove/rke-log-linker] Removing container on host [172.27.116.67]
INFO[0403] Removing container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0404] [remove/rke-log-linker] Successfully removed container on host [172.27.116.67]
DEBU[0404] [controlplane] Successfully created log link for Container [kube-apiserver] on host [172.27.116.67]
DEBU[0404] [controlplane] Container [kube-controller-manager] is already running on host [172.27.116.67]
DEBU[0404] [controlplane] Checking if container [kube-controller-manager] is eligible for upgrade on host [172.27.116.67]
DEBU[0404] [controlplane] Container [kube-controller-manager] is not eligible for upgrade on host [172.27.116.67]
INFO[0404] [healthcheck] Start Healthcheck on service [kube-controller-manager] on host [172.27.116.67]
INFO[0404] [healthcheck] service [kube-controller-manager] on host [172.27.116.67] is healthy
DEBU[0404] [controlplane] Creating log link for Container [kube-controller-manager] on host [172.27.116.67]
DEBU[0404] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0404] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.67]
DEBU[0404] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0404] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0405] Starting container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0407] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.67]
DEBU[0407] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0408] [remove/rke-log-linker] Removing container on host [172.27.116.67]
INFO[0408] Removing container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0408] [remove/rke-log-linker] Successfully removed container on host [172.27.116.67]
DEBU[0408] [controlplane] Successfully created log link for Container [kube-controller-manager] on host [172.27.116.67]
DEBU[0408] [controlplane] Container [kube-scheduler] is already running on host [172.27.116.67]
DEBU[0408] [controlplane] Checking if container [kube-scheduler] is eligible for upgrade on host [172.27.116.67]
DEBU[0408] [controlplane] Container [kube-scheduler] is not eligible for upgrade on host [172.27.116.67]
INFO[0408] [healthcheck] Start Healthcheck on service [kube-scheduler] on host [172.27.116.67]
INFO[0408] [healthcheck] service [kube-scheduler] on host [172.27.116.67] is healthy
DEBU[0408] [controlplane] Creating log link for Container [kube-scheduler] on host [172.27.116.67]
DEBU[0408] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0408] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.67]
DEBU[0408] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0408] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0410] Starting container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0411] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.67]
DEBU[0411] [remove/rke-log-linker] Checking if container is running on host [172.27.116.67]
DEBU[0412] [remove/rke-log-linker] Removing container on host [172.27.116.67]
INFO[0412] Removing container [rke-log-linker] on host [172.27.116.67], try #1
INFO[0413] [remove/rke-log-linker] Successfully removed container on host [172.27.116.67]
DEBU[0413] [controlplane] Successfully created log link for Container [kube-scheduler] on host [172.27.116.67]
INFO[0413] [controlplane] Now checking status of node ks-9047368, try #1
DEBU[0413] Checking node list for node [ks-9047368], try #1
DEBU[0413] [controlplane] Found node by name ks-9047368
DEBU[0413] Checking node list for node [ks-9047368], try #1
DEBU[0413] Checking node list for node [ks-9047368], try #1
DEBU[0413] Node ks-9047368 is already cordoned: false
INFO[0413] Processing controlplane host ks-9047988
INFO[0413] [controlplane] Now checking status of node ks-9047988, try #1
DEBU[0413] Checking node list for node [ks-9047988], try #1
DEBU[0413] [controlplane] Found node by name ks-9047988
INFO[0413] [controlplane] Getting list of nodes for upgrade
DEBU[0413] [controlplane] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.68]
DEBU[0413] [controlplane] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.68]
DEBU[0413] [controlplane] Checking if container [kube-apiserver] is eligible for upgrade on host [172.27.116.68]
DEBU[0413] [controlplane] Host ks-9047988 is upgradable because kube-apiserver needs to run
DEBU[0413] [worker] Checking if container [nginx-proxy] is eligible for upgrade on host [172.27.116.68]
DEBU[0413] [worker] Container [nginx-proxy] is eligible for upgrade on host [172.27.116.68]
DEBU[0413] [worker] Host ks-9047988 is upgradable because nginx-proxy has changed
DEBU[0413] [controlplane] Cordoning node ks-9047988
DEBU[0413] Checking node list for node [ks-9047988], try #1
DEBU[0413] Checking node list for node [ks-9047988], try #1
DEBU[0413] Node ks-9047988 is already cordoned: true
INFO[0413] Upgrading controlplane components for control host ks-9047988
DEBU[0413] [remove/nginx-proxy] Checking if container is running on host [172.27.116.68]
DEBU[0413] [remove/nginx-proxy] Removing container on host [172.27.116.68]
INFO[0413] Removing container [nginx-proxy] on host [172.27.116.68], try #1
INFO[0416] [remove/nginx-proxy] Successfully removed container on host [172.27.116.68]
INFO[0416] Checking if container [service-sidekick] is running on host [172.27.116.68], try #1
DEBU[0416] [sidekick] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.68]
DEBU[0416] [sidekick] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.68]
INFO[0416] [sidekick] Sidekick container already created on host [172.27.116.68]
DEBU[0416] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.68], try #1
INFO[0416] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.68]
INFO[0418] Starting container [kube-apiserver] on host [172.27.116.68], try #1
INFO[0420] [controlplane] Successfully started [kube-apiserver] container on host [172.27.116.68]
INFO[0420] [healthcheck] Start Healthcheck on service [kube-apiserver] on host [172.27.116.68]
DEBU[0420] [healthcheck] Failed to check https://localhost:6443/healthz for service [kube-apiserver] on host [172.27.116.68]: Get "https://localhost:6443/healthz": Unable to access the service on localhost:6443. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused), try #1
DEBU[0425] [healthcheck] Service [kube-apiserver] is not healthy on host [172.27.116.68]. Response code: [500], response body: [+]ping ok
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
, try #2
INFO[0430] [healthcheck] service [kube-apiserver] on host [172.27.116.68] is healthy
DEBU[0430] [controlplane] Creating log link for Container [kube-apiserver] on host [172.27.116.68]
DEBU[0430] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0430] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.68]
DEBU[0430] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0430] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0431] Starting container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0432] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.68]
DEBU[0432] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0434] [remove/rke-log-linker] Removing container on host [172.27.116.68]
INFO[0434] Removing container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0434] [remove/rke-log-linker] Successfully removed container on host [172.27.116.68]
DEBU[0434] [controlplane] Successfully created log link for Container [kube-apiserver] on host [172.27.116.68]
DEBU[0434] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.68], try #1
INFO[0434] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.68]
INFO[0435] Starting container [kube-controller-manager] on host [172.27.116.68], try #1
INFO[0438] [controlplane] Successfully started [kube-controller-manager] container on host [172.27.116.68]
INFO[0438] [healthcheck] Start Healthcheck on service [kube-controller-manager] on host [172.27.116.68]
DEBU[0438] [healthcheck] Failed to check https://localhost:10257/healthz for service [kube-controller-manager] on host [172.27.116.68]: Get "https://localhost:10257/healthz": Unable to access the service on localhost:10257. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused), try #1
INFO[0443] [healthcheck] service [kube-controller-manager] on host [172.27.116.68] is healthy
DEBU[0443] [controlplane] Creating log link for Container [kube-controller-manager] on host [172.27.116.68]
DEBU[0443] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0443] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.68]
DEBU[0443] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0443] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0444] Starting container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0446] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.68]
DEBU[0446] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0448] [remove/rke-log-linker] Removing container on host [172.27.116.68]
INFO[0448] Removing container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0449] [remove/rke-log-linker] Successfully removed container on host [172.27.116.68]
DEBU[0449] [controlplane] Successfully created log link for Container [kube-controller-manager] on host [172.27.116.68]
DEBU[0449] Checking if image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.68], try #1
INFO[0449] Image [rancher/hyperkube:v1.22.10-rancher1] exists on host [172.27.116.68]
INFO[0451] Starting container [kube-scheduler] on host [172.27.116.68], try #1
INFO[0454] [controlplane] Successfully started [kube-scheduler] container on host [172.27.116.68]
INFO[0454] [healthcheck] Start Healthcheck on service [kube-scheduler] on host [172.27.116.68]
DEBU[0454] [healthcheck] Failed to check http://localhost:10251/healthz for service [kube-scheduler] on host [172.27.116.68]: Get "http://localhost:10251/healthz": Unable to access the service on localhost:10251. The service might be still starting up. Error: ssh: rejected: connect failed (Connection refused), try #1
INFO[0459] [healthcheck] service [kube-scheduler] on host [172.27.116.68] is healthy
DEBU[0459] [controlplane] Creating log link for Container [kube-scheduler] on host [172.27.116.68]
DEBU[0459] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0459] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.68]
DEBU[0459] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0459] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0461] Starting container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0463] [controlplane] Successfully started [rke-log-linker] container on host [172.27.116.68]
DEBU[0463] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0465] [remove/rke-log-linker] Removing container on host [172.27.116.68]
INFO[0465] Removing container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0466] [remove/rke-log-linker] Successfully removed container on host [172.27.116.68]
DEBU[0466] [controlplane] Successfully created log link for Container [kube-scheduler] on host [172.27.116.68]
INFO[0466] Upgrading workerplane components for control host ks-9047988
INFO[0466] Checking if container [service-sidekick] is running on host [172.27.116.68], try #1
DEBU[0466] [sidekick] Checking if container [service-sidekick] is eligible for upgrade on host [172.27.116.68]
DEBU[0466] [sidekick] Container [service-sidekick] is not eligible for upgrade on host [172.27.116.68]
INFO[0466] [sidekick] Sidekick container already created on host [172.27.116.68]
DEBU[0466] [worker] Container [kubelet] is already running on host [172.27.116.68]
DEBU[0466] [worker] Checking if container [kubelet] is eligible for upgrade on host [172.27.116.68]
DEBU[0466] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0466] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0466] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0466] [worker] Container [kubelet] is not eligible for upgrade on host [172.27.116.68]
INFO[0466] [healthcheck] Start Healthcheck on service [kubelet] on host [172.27.116.68]
INFO[0466] [healthcheck] service [kubelet] on host [172.27.116.68] is healthy
DEBU[0466] [worker] Creating log link for Container [kubelet] on host [172.27.116.68]
DEBU[0466] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0466] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.68]
DEBU[0466] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0466] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0468] Starting container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0471] [worker] Successfully started [rke-log-linker] container on host [172.27.116.68]
DEBU[0471] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0473] [remove/rke-log-linker] Removing container on host [172.27.116.68]
INFO[0473] Removing container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0474] [remove/rke-log-linker] Successfully removed container on host [172.27.116.68]
DEBU[0474] [worker] Successfully created log link for Container [kubelet] on host [172.27.116.68]
DEBU[0474] [worker] Container [kube-proxy] is already running on host [172.27.116.68]
DEBU[0474] [worker] Checking if container [kube-proxy] is eligible for upgrade on host [172.27.116.68]
DEBU[0474] slice is not equal, showing data in new value which is not in old value: map[]
DEBU[0474] slice is not equal, showing data in old value which is not in new value: map[label=disable:{}]
DEBU[0474] returning equal as true because diff matches the automatically added disable label for SELinux which can be ignored: map[label=disable:{}]
DEBU[0474] [worker] Container [kube-proxy] is not eligible for upgrade on host [172.27.116.68]
INFO[0474] [healthcheck] Start Healthcheck on service [kube-proxy] on host [172.27.116.68]
INFO[0474] [healthcheck] service [kube-proxy] on host [172.27.116.68] is healthy
DEBU[0474] [worker] Creating log link for Container [kube-proxy] on host [172.27.116.68]
DEBU[0474] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0474] [remove/rke-log-linker] Container doesn't exist on host [172.27.116.68]
DEBU[0474] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0474] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
INFO[0475] Starting container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0479] [worker] Successfully started [rke-log-linker] container on host [172.27.116.68]
DEBU[0479] [remove/rke-log-linker] Checking if container is running on host [172.27.116.68]
DEBU[0481] [remove/rke-log-linker] Removing container on host [172.27.116.68]
INFO[0481] Removing container [rke-log-linker] on host [172.27.116.68], try #1
INFO[0482] [remove/rke-log-linker] Successfully removed container on host [172.27.116.68]
DEBU[0482] [worker] Successfully created log link for Container [kube-proxy] on host [172.27.116.68]
INFO[0482] [controlplane] Now checking status of node ks-9047988, try #1
DEBU[0482] Checking node list for node [ks-9047988], try #1
DEBU[0482] [controlplane] Found node by name ks-9047988
DEBU[0482] Checking node list for node [ks-9047988], try #1
DEBU[0482] Checking node list for node [ks-9047988], try #1
DEBU[0482] Node ks-9047988 is already cordoned: false
INFO[0482] [controlplane] Successfully upgraded Controller Plane..
DEBU[0482] Checking if cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0482] Cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0482] Enabling kube-api audit log for cluster version [v1.22.10-rancher1-1]
DEBU[0482] Host: 172.27.116.65 has role: etcd
DEBU[0482] Host: 172.27.116.65 has role: controlplane
DEBU[0482] Host: 172.27.116.65 has role: worker
DEBU[0482] Host: 172.27.116.66 has role: etcd
DEBU[0482] Host: 172.27.116.66 has role: controlplane
DEBU[0482] Host: 172.27.116.66 has role: worker
DEBU[0482] Host: 172.27.116.67 has role: etcd
DEBU[0482] Host: 172.27.116.67 has role: controlplane
DEBU[0482] Host: 172.27.116.67 has role: worker
DEBU[0482] Host: 172.27.116.68 has role: etcd
DEBU[0482] Host: 172.27.116.68 has role: controlplane
DEBU[0482] Host: 172.27.116.68 has role: worker
INFO[0482] [authz] Creating rke-job-deployer ServiceAccount
INFO[0483] [authz] rke-job-deployer ServiceAccount created successfully
INFO[0483] [authz] Creating system:node ClusterRoleBinding
INFO[0483] [authz] system:node ClusterRoleBinding created successfully
INFO[0483] [authz] Creating kube-apiserver proxy ClusterRole and ClusterRoleBinding
INFO[0483] [authz] kube-apiserver proxy ClusterRole and ClusterRoleBinding created successfully
INFO[0483] Successfully Deployed state file at [./cluster.rkestate]
INFO[0483] [state] Saving full cluster state to Kubernetes
INFO[0484] [state] Successfully Saved full cluster state to Kubernetes ConfigMap: full-cluster-state
DEBU[0484] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0484] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0484] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0484] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0484] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0484] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0484] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0484] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0484] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0484] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0484] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0484] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0484] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0484] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0484] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0484] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0484] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0484] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] Version [3.5.0] is equal or higher than version [3.2.99]
DEBU[0484] getDefaultKubernetesServicesOptions: getting serviceOptions for cluster version [v1.22.10-rancher1-1]
DEBU[0484] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0484] getDefaultKubernetesServicesOptions: serviceOptions found for cluster major version [v1.22]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] Extracted version [v1.22.10-rancher1] from image [rancher/hyperkube:v1.22.10-rancher1]
DEBU[0484] Extracted version [v3.5.0] from image [rancher/mirrored-coreos-etcd:v3.5.0]
DEBU[0484] etcd version [3.5.0] is higher than max version [3.4.3-rancher99] for advertising port 4001, not going to advertise port 4001
DEBU[0484] etcd version [3.5.0] is higher than max version [3.4.14-rancher99] for adding stricter TLS cipher suites, going to add stricter TLS cipher suites arguments to etcd
DEBU[0484] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0484] Version [3.5.0] is equal or higher than version [3.2.99]
INFO[0484] [worker] Upgrading Worker Plane..
INFO[0484] [worker] Successfully upgraded Worker Plane..
DEBU[0484] [cleanup] Starting log link cleanup on host [172.27.116.68]
DEBU[0484] [cleanup] Starting log link cleanup on host [172.27.116.65]
DEBU[0484] [cleanup] Starting log link cleanup on host [172.27.116.66]
DEBU[0484] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.65]
DEBU[0484] [cleanup] Starting log link cleanup on host [172.27.116.67]
DEBU[0484] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.67]
DEBU[0484] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.68]
DEBU[0484] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.66]
DEBU[0484] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.68]
DEBU[0484] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68], try #1
INFO[0484] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.68]
DEBU[0484] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.67]
DEBU[0484] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0484] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
DEBU[0484] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.65]
DEBU[0484] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
DEBU[0484] [remove/rke-log-cleaner] Container doesn't exist on host [172.27.116.66]
INFO[0484] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
DEBU[0484] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0484] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0484] Starting container [rke-log-cleaner] on host [172.27.116.65], try #1
INFO[0485] Starting container [rke-log-cleaner] on host [172.27.116.67], try #1
INFO[0485] Starting container [rke-log-cleaner] on host [172.27.116.66], try #1
INFO[0485] Starting container [rke-log-cleaner] on host [172.27.116.68], try #1
INFO[0486] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.65]
DEBU[0486] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.65]
INFO[0486] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.67]
DEBU[0486] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.67]
INFO[0486] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.66]
DEBU[0486] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.66]
DEBU[0487] [remove/rke-log-cleaner] Removing container on host [172.27.116.65]
INFO[0487] Removing container [rke-log-cleaner] on host [172.27.116.65], try #1
DEBU[0487] [remove/rke-log-cleaner] Removing container on host [172.27.116.67]
INFO[0487] Removing container [rke-log-cleaner] on host [172.27.116.67], try #1
INFO[0488] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.65]
DEBU[0488] [cleanup] Successfully cleaned up log links on host [172.27.116.65]
INFO[0488] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.67]
DEBU[0488] [cleanup] Successfully cleaned up log links on host [172.27.116.67]
DEBU[0488] [remove/rke-log-cleaner] Removing container on host [172.27.116.66]
INFO[0488] Removing container [rke-log-cleaner] on host [172.27.116.66], try #1
INFO[0488] [cleanup] Successfully started [rke-log-cleaner] container on host [172.27.116.68]
DEBU[0488] [remove/rke-log-cleaner] Checking if container is running on host [172.27.116.68]
INFO[0489] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.66]
DEBU[0489] [cleanup] Successfully cleaned up log links on host [172.27.116.66]
DEBU[0491] [remove/rke-log-cleaner] Removing container on host [172.27.116.68]
INFO[0491] Removing container [rke-log-cleaner] on host [172.27.116.68], try #1
INFO[0491] [remove/rke-log-cleaner] Successfully removed container on host [172.27.116.68]
DEBU[0491] [cleanup] Successfully cleaned up log links on host [172.27.116.68]
INFO[0491] [sync] Syncing nodes Labels and Taints
DEBU[0491] worker [9] starting sync for node [ks-9047366]
DEBU[0491] Checking node list for node [ks-9047366], try #1
DEBU[0491] worker [2] starting sync for node [ks-9047988]
DEBU[0491] Checking node list for node [ks-9047988], try #1
DEBU[0491] worker [4] starting sync for node [ks-9047368]
DEBU[0491] Checking node list for node [ks-9047368], try #1
DEBU[0491] worker [0] starting sync for node [ks-9047489]
DEBU[0491] Checking node list for node [ks-9047489], try #1
DEBU[0491] skipping syncing labels for node [ks-9047366]
DEBU[0491] skipping syncing labels for node [ks-9047368]
DEBU[0491] skipping syncing labels for node [ks-9047489]
INFO[0492] [sync] Successfully synced nodes Labels and Taints
DEBU[0492] Checking if cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0492] Cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0492] Enabling kube-api audit log for cluster version [v1.22.10-rancher1-1]
DEBU[0492] Host: 172.27.116.65 has role: etcd
DEBU[0492] Host: 172.27.116.65 has role: controlplane
DEBU[0492] Host: 172.27.116.65 has role: worker
DEBU[0492] Host: 172.27.116.66 has role: etcd
DEBU[0492] Host: 172.27.116.66 has role: controlplane
DEBU[0492] Host: 172.27.116.66 has role: worker
DEBU[0492] Host: 172.27.116.67 has role: etcd
DEBU[0492] Host: 172.27.116.67 has role: controlplane
DEBU[0492] Host: 172.27.116.67 has role: worker
DEBU[0492] Host: 172.27.116.68 has role: etcd
DEBU[0492] Host: 172.27.116.68 has role: controlplane
DEBU[0492] Host: 172.27.116.68 has role: worker
INFO[0492] [network] Setting up network plugin: flannel
INFO[0492] [addons] Saving ConfigMap for addon rke-network-plugin to Kubernetes
INFO[0492] [addons] Successfully saved ConfigMap for addon rke-network-plugin to Kubernetes
INFO[0492] [addons] Executing deploy job rke-network-plugin
DEBU[0492] Checking node list for node [ks-9047489], try #1
DEBU[0492] Checking addon job OS label for cluster version [v1.22.10-rancher1-1]
DEBU[0492] Cluster version [v1.22.10-rancher1-1] needs to use new OS label
DEBU[0492] [k8s] Job rke-network-plugin-deploy-job already exists..
INFO[0492] [addons] Setting up coredns
INFO[0492] [addons] Saving ConfigMap for addon rke-coredns-addon to Kubernetes
INFO[0492] [addons] Successfully saved ConfigMap for addon rke-coredns-addon to Kubernetes
INFO[0492] [addons] Executing deploy job rke-coredns-addon
DEBU[0492] Checking node list for node [ks-9047489], try #1
DEBU[0492] Checking addon job OS label for cluster version [v1.22.10-rancher1-1]
DEBU[0492] Cluster version [v1.22.10-rancher1-1] needs to use new OS label
DEBU[0492] [k8s] Job rke-coredns-addon-deploy-job already exists..
INFO[0492] [addons] CoreDNS deployed successfully
INFO[0492] [dns] DNS provider coredns deployed successfully
INFO[0492] [addons] Setting up Metrics Server
INFO[0492] [addons] Saving ConfigMap for addon rke-metrics-addon to Kubernetes
INFO[0492] [addons] Successfully saved ConfigMap for addon rke-metrics-addon to Kubernetes
INFO[0492] [addons] Executing deploy job rke-metrics-addon
DEBU[0492] Checking node list for node [ks-9047489], try #1
DEBU[0492] Checking addon job OS label for cluster version [v1.22.10-rancher1-1]
DEBU[0492] Cluster version [v1.22.10-rancher1-1] needs to use new OS label
DEBU[0492] [k8s] Job rke-metrics-addon-deploy-job already exists..
INFO[0492] [addons] Metrics Server deployed successfully
INFO[0492] [ingress] Setting up nginx ingress controller
INFO[0492] [ingress] removing admission batch jobs if they exist
INFO[0493] [addons] Saving ConfigMap for addon rke-ingress-controller to Kubernetes
INFO[0493] [addons] Successfully saved ConfigMap for addon rke-ingress-controller to Kubernetes
INFO[0493] [addons] Executing deploy job rke-ingress-controller
DEBU[0493] Checking node list for node [ks-9047489], try #1
DEBU[0493] Checking addon job OS label for cluster version [v1.22.10-rancher1-1]
DEBU[0493] Cluster version [v1.22.10-rancher1-1] needs to use new OS label
DEBU[0493] [k8s] Job rke-ingress-controller-deploy-job already exists..
INFO[0493] [ingress] removing default backend service and deployment if they exist
INFO[0493] [ingress] ingress controller nginx deployed successfully
INFO[0493] [addons] Setting up user addons
INFO[0493] [addons] no user addons defined
INFO[0493] Finished building Kubernetes cluster successfully
root@ks-9047489:~#
```  