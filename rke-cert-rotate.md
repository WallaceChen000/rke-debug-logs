## rke cert rotate  
```sh  
root@ks-9047489:~# rke --debug cert rotate
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
INFO[0000] Rotating Kubernetes cluster certificates
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
INFO[0000] [certificates] GenerateServingCertificate is disabled, checking if there are unused kubelet certificates
INFO[0000] [certificates] Generating Kubernetes API server certificates
INFO[0000] [certificates] Generating Kube Controller certificates
INFO[0000] [certificates] Generating Kube Scheduler certificates
INFO[0000] [certificates] Generating Kube Proxy certificates
INFO[0001] [certificates] Generating Node certificate
INFO[0001] [certificates] Generating admin certificates and kubeconfig
INFO[0001] [certificates] Generating Kubernetes API server proxy client certificates
INFO[0001] [certificates] Generating kube-etcd-172-27-116-55 certificate and key
INFO[0002] [certificates] Generating kube-etcd-172-27-116-56 certificate and key
INFO[0002] [certificates] Generating kube-etcd-172-27-116-57 certificate and key
INFO[0002] Successfully Deployed state file at [./cluster.rkestate]
DEBU[0002] Checking if cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0002] Cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0002] Enabling kube-api audit log for cluster version [v1.22.10-rancher1-1]
DEBU[0002] Host: 172.27.116.65 has role: etcd
DEBU[0002] Host: 172.27.116.65 has role: controlplane
DEBU[0002] Host: 172.27.116.65 has role: worker
DEBU[0002] Host: 172.27.116.66 has role: etcd
DEBU[0002] Host: 172.27.116.66 has role: controlplane
DEBU[0002] Host: 172.27.116.66 has role: worker
DEBU[0002] Host: 172.27.116.67 has role: etcd
DEBU[0002] Host: 172.27.116.67 has role: controlplane
DEBU[0002] Host: 172.27.116.67 has role: worker
INFO[0002] Rebuilding Kubernetes cluster with rotated certificates
DEBU[0002] Checking if cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0002] Cluster version [1.22.10-rancher1-1] needs to have kube-api audit log enabled
DEBU[0002] Enabling kube-api audit log for cluster version [v1.22.10-rancher1-1]
DEBU[0002] Host: 172.27.116.65 has role: etcd
DEBU[0002] Host: 172.27.116.65 has role: controlplane
DEBU[0002] Host: 172.27.116.65 has role: worker
DEBU[0002] Host: 172.27.116.66 has role: etcd
DEBU[0002] Host: 172.27.116.66 has role: controlplane
DEBU[0002] Host: 172.27.116.66 has role: worker
DEBU[0002] Host: 172.27.116.67 has role: etcd
DEBU[0002] Host: 172.27.116.67 has role: controlplane
DEBU[0002] Host: 172.27.116.67 has role: worker
INFO[0002] [dialer] Setup tunnel for host [172.27.116.67]
INFO[0002] [dialer] Setup tunnel for host [172.27.116.65]
DEBU[0002] Connecting to Docker API for host [172.27.116.67]
DEBU[0002] Connecting to Docker API for host [172.27.116.65]
INFO[0002] [dialer] Setup tunnel for host [172.27.116.66]
DEBU[0002] Connecting to Docker API for host [172.27.116.66]
DEBU[0002] Docker Info found for host [172.27.116.67]: types.Info{ID:"VN5L:TH7K:7SRQ:LLCZ:F7QU:TJUR:7AZ7:ETFA:NIKN:KE4N:OEJE:KWUZ", Containers:50, ContainersRunning:44, ContainersPaused:0, ContainersStopped:6, Images:32, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:185, OomKillDisable:true, NGoroutines:157, SystemTime:"2023-02-22T17:38:56.091767026+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc000476310), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047368", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
DEBU[0002] Docker Info found for host [172.27.116.66]: types.Info{ID:"7T67:DXEC:PYY6:VISK:5RG4:M2UV:N6NE:MAI4:QNBJ:PXN6:JNZ3:E6XT", Containers:45, ContainersRunning:41, ContainersPaused:0, ContainersStopped:4, Images:43, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:168, OomKillDisable:true, NGoroutines:148, SystemTime:"2023-02-22T17:38:56.3159533+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc000148150), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047366", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
DEBU[0002] Docker Info found for host [172.27.116.65]: types.Info{ID:"PXEX:4WFR:EIA2:YQWO:7QYJ:AV77:D5FS:5CXU:O7VZ:7V3L:V24Y:IHH2", Containers:140, ContainersRunning:98, ContainersPaused:0, ContainersStopped:42, Images:47, Driver:"btrfs", DriverStatus:[][2]string{[2]string{"Build Version", "Btrfs v4.9.1"}, [2]string{"Library Version", "102"}}, SystemStatus:[][2]string(nil), Plugins:types.PluginsInfo{Volume:[]string{"local"}, Network:[]string{"bridge", "host", "ipvlan", "macvlan", "null", "overlay"}, Authorization:[]string(nil), Log:[]string{"awslogs", "fluentd", "gcplogs", "gelf", "journald", "json-file", "local", "logentries", "splunk", "syslog"}}, MemoryLimit:true, SwapLimit:true, KernelMemory:true, KernelMemoryTCP:true, CPUCfsPeriod:true, CPUCfsQuota:true, CPUShares:true, CPUSet:true, PidsLimit:true, IPv4Forwarding:true, BridgeNfIptables:true, BridgeNfIP6tables:true, Debug:false, NFd:466, OomKillDisable:true, NGoroutines:369, SystemTime:"2023-02-22T17:38:55.770257329+08:00", LoggingDriver:"json-file", CgroupDriver:"cgroupfs", CgroupVersion:"1", NEventsListener:1, KernelVersion:"4.19.0_ift-kernel", OperatingSystem:"CentOS Linux 7 (Core)", OSVersion:"7", OSType:"linux", Architecture:"x86_64", IndexServerAddress:"https://index.docker.io/v1/", RegistryConfig:(*registry.ServiceConfig)(0xc000476850), NCPU:23, MemTotal:19419557888, GenericResources:[]swarm.GenericResource(nil), DockerRootDir:"/var/lib/docker", HTTPProxy:"", HTTPSProxy:"", NoProxy:"", Name:"ks-9047489", Labels:[]string{}, ExperimentalBuild:false, ServerVersion:"20.10.7", ClusterStore:"", ClusterAdvertise:"", Runtimes:map[string]types.Runtime{"io.containerd.runc.v2":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "io.containerd.runtime.v1.linux":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "nvidia":types.Runtime{Path:"/usr/bin/nvidia-container-runtime", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}, "runc":types.Runtime{Path:"runc", Args:[]string(nil), Shim:(*types.ShimConfig)(nil)}}, DefaultRuntime:"nvidia", Swarm:swarm.Info{NodeID:"", NodeAddr:"", LocalNodeState:"inactive", ControlAvailable:false, Error:"", RemoteManagers:[]swarm.Peer(nil), Nodes:0, Managers:0, Cluster:(*swarm.ClusterInfo)(nil), Warnings:[]string(nil)}, LiveRestoreEnabled:false, Isolation:"", InitBinary:"docker-init", ContainerdCommit:types.Commit{ID:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16", Expected:"212e8b6fa2f44b9c21b2798135fc6fb7c53efc16"}, RuncCommit:types.Commit{ID:"v1.1.1-0-g52de29d", Expected:"v1.1.1-0-g52de29d"}, InitCommit:types.Commit{ID:"de40ad0", Expected:"de40ad0"}, SecurityOptions:[]string{"name=seccomp,profile=default"}, ProductLicense:"", DefaultAddressPools:[]types.NetworkAddressPool(nil), Warnings:[]string(nil)}
INFO[0002] [certificates] Deploying kubernetes certificates to Cluster nodes
INFO[0002] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
INFO[0002] Checking if container [cert-deployer] is running on host [172.27.116.67], try #1
INFO[0002] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
DEBU[0002] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66], try #1
INFO[0002] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.66]
DEBU[0002] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0002] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67], try #1
INFO[0002] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.67]
DEBU[0002] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0002] Checking if image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65], try #1
INFO[0002] Image [rancher/rke-tools:v0.1.80] exists on host [172.27.116.65]
DEBU[0002] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
INFO[0003] Starting container [cert-deployer] on host [172.27.116.67], try #1
INFO[0003] Starting container [cert-deployer] on host [172.27.116.66], try #1
INFO[0004] Starting container [cert-deployer] on host [172.27.116.65], try #1
DEBU[0004] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0004] Checking if container [cert-deployer] is running on host [172.27.116.67], try #1
DEBU[0005] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0005] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
DEBU[0005] [certificates] Successfully started Certificate deployer container: cert-deployer
INFO[0005] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0009] Checking if container [cert-deployer] is running on host [172.27.116.67], try #1
INFO[0009] Removing container [cert-deployer] on host [172.27.116.67], try #1
INFO[0010] Checking if container [cert-deployer] is running on host [172.27.116.66], try #1
INFO[0010] Removing container [cert-deployer] on host [172.27.116.66], try #1
INFO[0010] Checking if container [cert-deployer] is running on host [172.27.116.65], try #1
INFO[0010] Removing container [cert-deployer] on host [172.27.116.65], try #1
INFO[0011] [reconcile] Rebuilding and updating local kube config
DEBU[0011] [reconcile] Rebuilding and updating local kube config, creating new kubeconfig
DEBU[0011] Deploying admin Kubeconfig locally at [./kube_config_cluster.yml]
INFO[0011] Successfully Deployed local admin kubeconfig at [./kube_config_cluster.yml]
DEBU[0011] [version] Using ./kube_config_cluster.yml to connect to Kubernetes cluster..
DEBU[0011] [version] Getting Kubernetes server version..
WARN[0026] [reconcile] host [172.27.116.65] is a control plane node without reachable Kubernetes API endpoint in the cluster
DEBU[0026] [reconcile] Rebuilding and updating local kube config, creating new kubeconfig
DEBU[0026] Deploying admin Kubeconfig locally at [./kube_config_cluster.yml]
INFO[0026] Successfully Deployed local admin kubeconfig at [./kube_config_cluster.yml]
DEBU[0026] [version] Using ./kube_config_cluster.yml to connect to Kubernetes cluster..
DEBU[0026] [version] Getting Kubernetes server version..
WARN[0036] [reconcile] host [172.27.116.66] is a control plane node without reachable Kubernetes API endpoint in the cluster
DEBU[0036] [reconcile] Rebuilding and updating local kube config, creating new kubeconfig
DEBU[0036] Deploying admin Kubeconfig locally at [./kube_config_cluster.yml]
INFO[0036] Successfully Deployed local admin kubeconfig at [./kube_config_cluster.yml]
DEBU[0036] [version] Using ./kube_config_cluster.yml to connect to Kubernetes cluster..
DEBU[0036] [version] Getting Kubernetes server version..
WARN[0036] [reconcile] host [172.27.116.67] is a control plane node without reachable Kubernetes API endpoint in the cluster
WARN[0036] [reconcile] no control plane node with reachable Kubernetes API endpoint in the cluster found
INFO[0036] [certificates] Successfully deployed kubernetes certificates to Cluster nodes
INFO[0036] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.65]
DEBU[0036] [remove/file-deployer] Checking if container is running on host [172.27.116.65]
DEBU[0036] [remove/file-deployer] Container doesn't exist on host [172.27.116.65]
DEBU[0036] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0036] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65], try #1
INFO[0036] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.65]
INFO[0037] Starting container [file-deployer] on host [172.27.116.65], try #1
INFO[0038] Successfully started [file-deployer] container on host [172.27.116.65]
INFO[0038] Waiting for [file-deployer] container to exit on host [172.27.116.65]
INFO[0038] Waiting for [file-deployer] container to exit on host [172.27.116.65]
DEBU[0041] Exit code for [file-deployer] container on host [172.27.116.65] is [0]
DEBU[0041] [remove/file-deployer] Checking if container is running on host [172.27.116.65]
DEBU[0041] [remove/file-deployer] Removing container on host [172.27.116.65]
INFO[0041] Removing container [file-deployer] on host [172.27.116.65], try #1
INFO[0041] [remove/file-deployer] Successfully removed container on host [172.27.116.65]
DEBU[0041] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.65]
INFO[0041] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.66]
DEBU[0041] [remove/file-deployer] Checking if container is running on host [172.27.116.66]
DEBU[0041] [remove/file-deployer] Container doesn't exist on host [172.27.116.66]
DEBU[0041] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0041] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66], try #1
INFO[0041] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.66]
INFO[0042] Starting container [file-deployer] on host [172.27.116.66], try #1
INFO[0044] Successfully started [file-deployer] container on host [172.27.116.66]
INFO[0044] Waiting for [file-deployer] container to exit on host [172.27.116.66]
INFO[0044] Waiting for [file-deployer] container to exit on host [172.27.116.66]
DEBU[0045] Exit code for [file-deployer] container on host [172.27.116.66] is [0]
DEBU[0045] [remove/file-deployer] Checking if container is running on host [172.27.116.66]
DEBU[0045] [remove/file-deployer] Removing container on host [172.27.116.66]
INFO[0045] Removing container [file-deployer] on host [172.27.116.66], try #1
INFO[0045] [remove/file-deployer] Successfully removed container on host [172.27.116.66]
DEBU[0045] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.66]
INFO[0045] [file-deploy] Deploying file [/etc/kubernetes/audit-policy.yaml] to node [172.27.116.67]
DEBU[0045] [remove/file-deployer] Checking if container is running on host [172.27.116.67]
DEBU[0045] [remove/file-deployer] Container doesn't exist on host [172.27.116.67]
DEBU[0045] SemVerMatchRange: Cluster version [v1.22.10-rancher1-1] matches range [>=1.22.0-rancher0]
DEBU[0045] Checking if image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67], try #1
INFO[0045] Image [rancher/rke-tools:v0.1.78] exists on host [172.27.116.67]
INFO[0046] Starting container [file-deployer] on host [172.27.116.67], try #1
INFO[0047] Successfully started [file-deployer] container on host [172.27.116.67]
INFO[0047] Waiting for [file-deployer] container to exit on host [172.27.116.67]
INFO[0047] Waiting for [file-deployer] container to exit on host [172.27.116.67]
DEBU[0048] Exit code for [file-deployer] container on host [172.27.116.67] is [0]
DEBU[0048] [remove/file-deployer] Checking if container is running on host [172.27.116.67]
DEBU[0048] [remove/file-deployer] Removing container on host [172.27.116.67]
INFO[0048] Removing container [file-deployer] on host [172.27.116.67], try #1
INFO[0049] [remove/file-deployer] Successfully removed container on host [172.27.116.67]
DEBU[0049] [file-deploy] Successfully deployed file [/etc/kubernetes/audit-policy.yaml] on node [172.27.116.67]
INFO[0049] [/etc/kubernetes/audit-policy.yaml] Successfully deployed audit policy file to Cluster control nodes
INFO[0049] Successfully Deployed state file at [./cluster.rkestate]
INFO[0049] [state] Saving full cluster state to Kubernetes
INFO[0081] [state] Saving full cluster state to Kubernetes
INFO[0113] [state] Saving full cluster state to Kubernetes
WARN[0145] Failed to save full cluster state to Kubernetes
INFO[0145] [etcd] Restarting up etcd plane..
DEBU[0145] [restart/etcd] Checking if container is running on host [172.27.116.65]
DEBU[0145] [restart/etcd] Checking if container is running on host [172.27.116.67]
DEBU[0145] [restart/etcd] Checking if container is running on host [172.27.116.66]
DEBU[0145] [restart/etcd] Restarting container on host [172.27.116.67]
INFO[0145] Restarting container [etcd] on host [172.27.116.67], try #1
DEBU[0145] [restart/etcd] Restarting container on host [172.27.116.65]
INFO[0145] Restarting container [etcd] on host [172.27.116.65], try #1
DEBU[0145] [restart/etcd] Restarting container on host [172.27.116.66]
INFO[0145] Restarting container [etcd] on host [172.27.116.66], try #1
INFO[0146] [restart/etcd] Successfully restarted container on host [172.27.116.65]
INFO[0147] [restart/etcd] Successfully restarted container on host [172.27.116.67]
INFO[0147] [restart/etcd] Successfully restarted container on host [172.27.116.66]
INFO[0147] [etcd] Successfully restarted etcd plane..
INFO[0147] [controlplane] Check if rotating a legacy cluster
FATA[0147] Error: No such container: kube-apiserver
root@ks-9047489:~#

```  