W0919 08:17:55.859445   17924 new_cluster.go:1435] Gossip is deprecated, using None DNS instead

I0919 08:17:55.859953   17924 new_cluster.go:1454] Cloud Provider ID: "aws"

I0919 08:17:58.352923   17924 subnets.go:224] Assigned CIDR 172.20.0.0/16 to subnet us-east-1a

### Previewing changes that will be made: ###

I0919 08:18:26.448600   17924 builder.go:312] asset "https://dl.k8s.io/release/v1.30.2/bin/linux/amd64/kubelet" is not well-known, downloading hash

I0919 08:18:40.171563   17924 builder.go:312] asset "https://dl.k8s.io/release/v1.30.2/bin/linux/amd64/kubectl" is not well-known, downloading hash

I0919 08:18:40.545956   17924 builder.go:312] asset "https://github.com/containerd/containerd/releases/download/v1.7.16/containerd-1.7.16-linux-amd64.tar.gz" is not well-known, downloading hash

I0919 08:18:42.477136   17924 builder.go:312] asset "https://artifacts.k8s.io/binaries/kops/1.30.0/linux/amd64/nodeup" is not well-known, downloading hash

I0919 08:18:51.087832   17924 builder.go:312] asset "https://dl.k8s.io/release/v1.30.2/bin/linux/arm64/kubelet" is not well-known, downloading hash

I0919 08:18:51.417568   17924 builder.go:312] asset "https://dl.k8s.io/release/v1.30.2/bin/linux/arm64/kubectl" is not well-known, downloading hash

I0919 08:18:51.804166   17924 builder.go:312] asset "https://github.com/containerd/containerd/releases/download/v1.7.16/containerd-1.7.16-linux-arm64.tar.gz" is not well-known, downloading hash

I0919 08:18:53.830175   17924 builder.go:312] asset "https://artifacts.k8s.io/binaries/kops/1.30.0/linux/arm64/nodeup" is not well-known, downloading hash

I0919 08:18:58.744425   17924 builder.go:312] asset "https://artifacts.k8s.io/binaries/kops/1.30.0/linux/amd64/protokube" is not well-known, downloading hash

I0919 08:18:59.110620   17924 builder.go:312] asset "https://artifacts.k8s.io/binaries/kops/1.30.0/linux/arm64/protokube" is not well-known, downloading hash

I0919 08:18:59.512969   17924 builder.go:312] asset "https://artifacts.k8s.io/binaries/kops/1.30.0/linux/amd64/channels" is not well-known, downloading hash

I0919 08:18:59.861459   17924 builder.go:312] asset "https://artifacts.k8s.io/binaries/kops/1.30.0/linux/arm64/channels" is not well-known, downloading hash

I0919 08:19:19.822773   17924 executor.go:113] Tasks: 0 done / 117 total; 43 can run

W0919 08:19:23.816488   17924 vfs_keystorereader.go:143] CA private key was not found

I0919 08:19:24.034958   17924 executor.go:113] Tasks: 43 done / 117 total; 22 can run

I0919 08:19:24.892261   17924 executor.go:113] Tasks: 65 done / 117 total; 34 can run

I0919 08:19:26.742171   17924 executor.go:113] Tasks: 99 done / 117 total; 4 can run

I0919 08:19:27.719342   17924 executor.go:113] Tasks: 103 done / 117 total; 6 can run

I0919 08:19:28.350285   17924 executor.go:113] Tasks: 109 done / 117 total; 2 can run

I0919 08:19:29.348009   17924 executor.go:113] Tasks: 111 done / 117 total; 4 can run

I0919 08:19:30.060231   17924 executor.go:113] Tasks: 115 done / 117 total; 2 can run

I0919 08:19:30.321448   17924 executor.go:113] Tasks: 117 done / 117 total; 0 can run

### Will create resources: ###

> AutoscalingGroup/control-plane-us-east-1a.masters.demok8scluster.k8s.local
> - Granularity             1Minute
> - InstanceProtection      false
> - LaunchTemplate          name:control-plane-us-east-1a.masters.demok8scluster.k8s.local
> - LoadBalancers           []
> - MaxInstanceLifetime     0
> - MaxSize                 1
> - Metrics                 [GroupDesiredCapacity, GroupInServiceInstances, GroupMaxSize, GroupMinSize, GroupPendingInstances, GroupStandbyInstances, GroupTerminatingInstances, GroupTotalInstances]
> - MinSize                 1
> - Subnets                 [name:us-east-1a.demok8scluster.k8s.local]
> - SuspendProcesses        []
> - Tags                    {Name: control-plane-us-east-1a.masters.demok8scluster.k8s.local, k8s.io/cluster-autoscaler/node-template/label/kops.k8s.io/kops-controller-pki: , k8s.io/cluster-autoscaler/node-template/label/node.kubernetes.io/exclude-from-external-load-balancers: , k8s.io/role/master: 1, k8s.io/role/control-plane: 1, kops.k8s.io/instancegroup: control-plane-us-east-1a, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, aws-node-termination-handler/managed: , k8s.io/cluster-autoscaler/node-template/label/node-role.kubernetes.io/control-plane: }
> - TargetGroups            [name:kops-controller-demok8scl-aprcdq id:kops-controller-demok8scl-aprcdq, name:tcp-demok8scluster-k8s-lo-aoh168 id:tcp-demok8scluster-k8s-lo-aoh168]

> AutoscalingGroup/nodes-us-east-1a.demok8scluster.k8s.local
> - Granularity             1Minute
> - InstanceProtection      false
> - LaunchTemplate          name:nodes-us-east-1a.demok8scluster.k8s.local
> - LoadBalancers           []
> - MaxInstanceLifetime     0
> - MaxSize                 1
> - Metrics                 [GroupDesiredCapacity, GroupInServiceInstances, GroupMaxSize, GroupMinSize, GroupPendingInstances, GroupStandbyInstances, GroupTerminatingInstances, GroupTotalInstances]
> - MinSize                 1
> - Subnets                 [name:us-east-1a.demok8scluster.k8s.local]
> - SuspendProcesses        []
> - Tags                    {k8s.io/role/node: 1, kops.k8s.io/instancegroup: nodes-us-east-1a, Name: nodes-us-east-1a.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, aws-node-termination-handler/managed: , k8s.io/cluster-autoscaler/node-template/label/node-role.kubernetes.io/node: }
> - TargetGroups            []

> AutoscalingLifecycleHook/control-plane-us-east-1a-NTHLifecycleHook
> - ID                      control-plane-us-east-1a-NTHLifecycleHook
> - AutoscalingGroup        name:control-plane-us-east-1a.masters.demok8scluster.k8s.local id:control-plane-us-east-1a.masters.demok8scluster.k8s.local
> - DefaultResult           CONTINUE
> - HeartbeatTimeout        300
> - LifecycleTransition     autoscaling:EC2_INSTANCE_TERMINATING
> - Enabled                 true

> AutoscalingLifecycleHook/nodes-us-east-1a-NTHLifecycleHook
> - ID                      nodes-us-east-1a-NTHLifecycleHook
> - AutoscalingGroup        name:nodes-us-east-1a.demok8scluster.k8s.local id:nodes-us-east-1a.demok8scluster.k8s.local
> - DefaultResult           CONTINUE
> - HeartbeatTimeout        300
> - LifecycleTransition     autoscaling:EC2_INSTANCE_TERMINATING
> - Enabled                 true

> DHCPOptions/demok8scluster.k8s.local
> - DomainName              ec2.internal
> - DomainNameServers       AmazonProvidedDNS
> - Shared                  false
> - Tags                    {Name: demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> EBSVolume/a.etcd-events.demok8scluster.k8s.local
> - AvailabilityZone        us-east-1a
> - Encrypted               true
> - SizeGB                  20
> - Tags                    {k8s.io/role/master: 1, kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: a.etcd-events.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, k8s.io/etcd/events: a/a, k8s.io/role/control-plane: 1}
> - VolumeIops              3000
> - VolumeThroughput        125
> - VolumeType              gp3

> EBSVolume/a.etcd-main.demok8scluster.k8s.local
> - AvailabilityZone        us-east-1a
> - Encrypted               true
> - SizeGB                  20
> - Tags                    {k8s.io/role/control-plane: 1, k8s.io/role/master: 1, kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: a.etcd-main.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, k8s.io/etcd/main: a/a}
> - VolumeIops              3000
> - VolumeThroughput        125
> - VolumeType              gp3

> EventBridgeRule/demok8scluster.k8s.local-ASGLifecycle
> - EventPattern            {"source":["aws.autoscaling"],"detail-type":["EC2 Instance-terminate Lifecycle Action"]}
> - SQSQueue                name:demok8scluster-k8s-local-nth
> - Tags                    {Name: demok8scluster.k8s.local-ASGLifecycle, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> EventBridgeRule/demok8scluster.k8s.local-InstanceScheduledChange
> - EventPattern            {"source": ["aws.health"],"detail-type": ["AWS Health Event"],"detail": {"service": ["EC2"],"eventTypeCategory": ["scheduledChange"]}}
> - SQSQueue                name:demok8scluster-k8s-local-nth
> - Tags                    {Name: demok8scluster.k8s.local-InstanceScheduledChange, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> EventBridgeRule/demok8scluster.k8s.local-InstanceStateChange
> - EventPattern            {"source": ["aws.ec2"],"detail-type": ["EC2 Instance State-change Notification"]}
> - SQSQueue                name:demok8scluster-k8s-local-nth
> - Tags                    {KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: demok8scluster.k8s.local-InstanceStateChange}

> EventBridgeRule/demok8scluster.k8s.local-SpotInterruption
> - EventPattern            {"source": ["aws.ec2"],"detail-type": ["EC2 Spot Instance Interruption Warning"]}
> - SQSQueue                name:demok8scluster-k8s-local-nth
> - Tags                    {Name: demok8scluster.k8s.local-SpotInterruption, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> EventBridgeTarget/demok8scluster.k8s.local-ASGLifecycle-Target
> - Rule                    name:demok8scluster.k8s.local-ASGLifecycle id:demok8scluster.k8s.local-ASGLifecycle
> - SQSQueue                name:demok8scluster-k8s-local-nth

> EventBridgeTarget/demok8scluster.k8s.local-InstanceScheduledChange-Target
> - Rule                    name:demok8scluster.k8s.local-InstanceScheduledChange id:demok8scluster.k8s.local-InstanceScheduledChange
> - SQSQueue                name:demok8scluster-k8s-local-nth

> EventBridgeTarget/demok8scluster.k8s.local-InstanceStateChange-Target
> - Rule                    name:demok8scluster.k8s.local-InstanceStateChange id:demok8scluster.k8s.local-InstanceStateChange
> - SQSQueue                name:demok8scluster-k8s-local-nth

> EventBridgeTarget/demok8scluster.k8s.local-SpotInterruption-Target
> - Rule                    name:demok8scluster.k8s.local-SpotInterruption id:demok8scluster.k8s.local-SpotInterruption
> - SQSQueue                name:demok8scluster-k8s-local-nth

> IAMInstanceProfile/masters.demok8scluster.k8s.local
> - Tags                    {Name: masters.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}
> - Shared                  false

> IAMInstanceProfile/nodes.demok8scluster.k8s.local
> - Tags                    {Name: nodes.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}
> - Shared                  false

> IAMInstanceProfileRole/masters.demok8scluster.k8s.local
> - InstanceProfile         name:masters.demok8scluster.k8s.local id:masters.demok8scluster.k8s.local
> - Role                    name:masters.demok8scluster.k8s.local

> IAMInstanceProfileRole/nodes.demok8scluster.k8s.local
> - InstanceProfile         name:nodes.demok8scluster.k8s.local id:nodes.demok8scluster.k8s.local
> - Role                    name:nodes.demok8scluster.k8s.local

> IAMRole/masters.demok8scluster.k8s.local
> - Tags                    {Name: masters.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}
> - ExportWithID            masters

> IAMRole/nodes.demok8scluster.k8s.local
> - Tags                    {KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: nodes.demok8scluster.k8s.local}
> - ExportWithID            nodes

> IAMRolePolicy/master-policyoverride
> - Role                    name:masters.demok8scluster.k8s.local
> - Managed                 true

> IAMRolePolicy/masters.demok8scluster.k8s.local
> - Role                    name:masters.demok8scluster.k8s.local
> - Managed                 false

> IAMRolePolicy/node-policyoverride
> - Role                    name:nodes.demok8scluster.k8s.local
> - Managed                 true

> IAMRolePolicy/nodes.demok8scluster.k8s.local
> - Role                    name:nodes.demok8scluster.k8s.local
> - Managed                 false

> InternetGateway/demok8scluster.k8s.local
> - VPC                     name:demok8scluster.k8s.local
> - Shared                  false
> - Tags                    {KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: demok8scluster.k8s.local}

> Keypair/apiserver-aggregator-ca
> - Subject                 cn=apiserver-aggregator-ca
> - Issuer
> - Type                    ca
> - LegacyFormat            false

> Keypair/etcd-clients-ca
> - Subject                 cn=etcd-clients-ca
> - Issuer
> - Type                    ca
> - LegacyFormat            false

> Keypair/etcd-manager-ca-events
> - Subject                 cn=etcd-manager-ca-events
> - Issuer
> - Type                    ca
> - LegacyFormat            false

> Keypair/etcd-manager-ca-main
> - Subject                 cn=etcd-manager-ca-main
> - Issuer
> - Type                    ca
> - LegacyFormat            false

> Keypair/etcd-peers-ca-events
> - Subject                 cn=etcd-peers-ca-events
> - Issuer
> - Type                    ca
> - LegacyFormat            false

> Keypair/etcd-peers-ca-main
> - Subject                 cn=etcd-peers-ca-main
> - Issuer
> - Type                    ca
> - LegacyFormat            false

> Keypair/kubernetes-ca
> - Subject                 cn=kubernetes-ca
> - Issuer
> - Type                    ca
> - LegacyFormat            false

> Keypair/service-account
> - Subject                 cn=service-account
> - Issuer
> - Type                    ca
> - LegacyFormat            false

> LaunchTemplate/control-plane-us-east-1a.masters.demok8scluster.k8s.local
> - AssociatePublicIP       true
> - CPUCredits
> - HTTPPutResponseHopLimit 1
> - HTTPTokens              required
> - HTTPProtocolIPv6        disabled
> - IAMInstanceProfile      name:masters.demok8scluster.k8s.local id:masters.demok8scluster.k8s.local
> - ImageID                 099720109477/ubuntu/images/hvm-ssd/ubuntu-jammy-22.04-amd64-server-20240607
> - InstanceMonitoring      false
> - InstanceType            t2.micro
> - IPv6AddressCount        0
> - RootVolumeIops          3000
> - RootVolumeSize          8
> - RootVolumeThroughput    125
> - RootVolumeType          gp3
> - RootVolumeEncryption    true
> - RootVolumeKmsKey
> - SecurityGroups          [name:masters.demok8scluster.k8s.local]
> - SpotPrice
> - Tags                    {k8s.io/role/master: 1, k8s.io/role/control-plane: 1, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, aws-node-termination-handler/managed: , k8s.io/cluster-autoscaler/node-template/label/kops.k8s.io/kops-controller-pki: , Name: control-plane-us-east-1a.masters.demok8scluster.k8s.local, k8s.io/cluster-autoscaler/node-template/label/node-role.kubernetes.io/control-plane: , k8s.io/cluster-autoscaler/node-template/label/node.kubernetes.io/exclude-from-external-load-balancers: , kops.k8s.io/instancegroup: control-plane-us-east-1a}

> LaunchTemplate/nodes-us-east-1a.demok8scluster.k8s.local
> - AssociatePublicIP       true
> - CPUCredits
> - HTTPPutResponseHopLimit 1
> - HTTPTokens              required
> - HTTPProtocolIPv6        disabled
> - IAMInstanceProfile      name:nodes.demok8scluster.k8s.local id:nodes.demok8scluster.k8s.local
> - ImageID                 099720109477/ubuntu/images/hvm-ssd/ubuntu-jammy-22.04-amd64-server-20240607
> - InstanceMonitoring      false
> - InstanceType            t2.micro
> - IPv6AddressCount        0
> - RootVolumeIops          3000
> - RootVolumeSize          8
> - RootVolumeThroughput    125
> - RootVolumeType          gp3
> - RootVolumeEncryption    true
> - RootVolumeKmsKey
> - SecurityGroups          [name:nodes.demok8scluster.k8s.local]
> - SpotPrice
> - Tags                    {kops.k8s.io/instancegroup: nodes-us-east-1a, Name: nodes-us-east-1a.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, aws-node-termination-handler/managed: , k8s.io/cluster-autoscaler/node-template/label/node-role.kubernetes.io/node: , k8s.io/role/node: 1}

> ManagedFile/cluster-completed.spec
> - Base                    s3://kops-ashu-storage/demok8scluster.k8s.local
> - Location                cluster-completed.spec

> ManagedFile/demok8scluster.k8s.local-addons-aws-cloud-controller.addons.k8s.io-k8s-1.18
> - Location                addons/aws-cloud-controller.addons.k8s.io/k8s-1.18.yaml

> ManagedFile/demok8scluster.k8s.local-addons-aws-ebs-csi-driver.addons.k8s.io-k8s-1.17
> - Location                addons/aws-ebs-csi-driver.addons.k8s.io/k8s-1.17.yaml

> ManagedFile/demok8scluster.k8s.local-addons-bootstrap
> - Location                addons/bootstrap-channel.yaml

> ManagedFile/demok8scluster.k8s.local-addons-coredns.addons.k8s.io-k8s-1.12
> - Location                addons/coredns.addons.k8s.io/k8s-1.12.yaml

> ManagedFile/demok8scluster.k8s.local-addons-kops-controller.addons.k8s.io-k8s-1.16
> - Location                addons/kops-controller.addons.k8s.io/k8s-1.16.yaml

> ManagedFile/demok8scluster.k8s.local-addons-kubelet-api.rbac.addons.k8s.io-k8s-1.9
> - Location                addons/kubelet-api.rbac.addons.k8s.io/k8s-1.9.yaml

> ManagedFile/demok8scluster.k8s.local-addons-limit-range.addons.k8s.io
> - Location                addons/limit-range.addons.k8s.io/v1.5.0.yaml

> ManagedFile/demok8scluster.k8s.local-addons-networking.cilium.io-k8s-1.16
> - Location                addons/networking.cilium.io/k8s-1.16-v1.15.yaml

> ManagedFile/demok8scluster.k8s.local-addons-node-termination-handler.aws-k8s-1.11
> - Location                addons/node-termination-handler.aws/k8s-1.11.yaml

> ManagedFile/demok8scluster.k8s.local-addons-storage-aws.addons.k8s.io-v1.15.0
> - Location                addons/storage-aws.addons.k8s.io/v1.15.0.yaml

> ManagedFile/etcd-cluster-spec-events
> - Base                    s3://kops-ashu-storage/demok8scluster.k8s.local/backups/etcd/events
> - Location                /control/etcd-cluster-spec

> ManagedFile/etcd-cluster-spec-main
> - Base                    s3://kops-ashu-storage/demok8scluster.k8s.local/backups/etcd/main
> - Location                /control/etcd-cluster-spec

> ManagedFile/kops-version.txt
> - Base                    s3://kops-ashu-storage/demok8scluster.k8s.local
> - Location                kops-version.txt

> ManagedFile/manifests-etcdmanager-events-control-plane-us-east-1a
> - Location                manifests/etcd/events-control-plane-us-east-1a.yaml

> ManagedFile/manifests-etcdmanager-main-control-plane-us-east-1a
> - Location                manifests/etcd/main-control-plane-us-east-1a.yaml

> ManagedFile/manifests-static-kube-apiserver-healthcheck
> - Location                manifests/static/kube-apiserver-healthcheck.yaml

> ManagedFile/nodeupconfig-control-plane-us-east-1a
> - Location                igconfig/control-plane/control-plane-us-east-1a/nodeupconfig.yaml

> ManagedFile/nodeupconfig-nodes-us-east-1a
> - Location                igconfig/node/nodes-us-east-1a/nodeupconfig.yaml

> NetworkLoadBalancer/api.demok8scluster.k8s.local
> - LoadBalancerBaseName    api-demok8scluster-k8s-lo-e44l8v
> - CLBName                 api.demok8scluster.k8s.local
> - SubnetMappings          [{"Subnet":{"Name":"us-east-1a.demok8scluster.k8s.local","ShortName":"us-east-1a","Lifecycle":"Sync","ID":null,"VPC":{"Name":"demok8scluster.k8s.local","Lifecycle":"Sync","ID":null,"CIDR":"172.20.0.0/16","AmazonIPv6":true,"IPv6CIDR":null,"EnableDNSHostnames":true,"EnableDNSSupport":true,"Shared":false,"Tags":{"KubernetesCluster":"demok8scluster.k8s.local","Name":"demok8scluster.k8s.local","kubernetes.io/cluster/demok8scluster.k8s.local":"owned"},"AssociateExtraCIDRBlocks":null},"VPCCIDRBlock":null,"AmazonIPv6CIDR":null,"AvailabilityZone":"us-east-1a","CIDR":"172.20.0.0/16","IPv6CIDR":null,"ResourceBasedNaming":true,"AssignIPv6AddressOnCreation":false,"Shared":false,"Tags":{"KubernetesCluster":"demok8scluster.k8s.local","Name":"us-east-1a.demok8scluster.k8s.local","SubnetType":"Public","kubernetes.io/cluster/demok8scluster.k8s.local":"owned","kubernetes.io/role/elb":"1","kubernetes.io/role/internal-elb":"1"}},"PrivateIPv4Address":null,"AllocationID":null}]
> - SecurityGroups          [name:api-elb.demok8scluster.k8s.local]
> - Scheme                  internet-facing
> - CrossZoneLoadBalancing  true
> - IpAddressType           ipv4
> - Tags                    {KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: api.demok8scluster.k8s.local}
> - Type                    network
> - VPC                     name:demok8scluster.k8s.local
> - AccessLog               {"Enabled":false,"S3BucketName":null,"S3BucketPrefix":null}
> - WellKnownServices       [kube-apiserver, kops-controller]

> NetworkLoadBalancerListener/api.demok8scluster.k8s.local-3988
> - NetworkLoadBalancer     name:api.demok8scluster.k8s.local id:api.demok8scluster.k8s.local
> - Port                    3988
> - TargetGroup             name:kops-controller-demok8scl-aprcdq id:kops-controller-demok8scl-aprcdq
> - SSLCertificateID
> - SSLPolicy

> NetworkLoadBalancerListener/api.demok8scluster.k8s.local-443
> - NetworkLoadBalancer     name:api.demok8scluster.k8s.local id:api.demok8scluster.k8s.local
> - Port                    443
> - TargetGroup             name:tcp-demok8scluster-k8s-lo-aoh168 id:tcp-demok8scluster-k8s-lo-aoh168
> - SSLCertificateID
> - SSLPolicy

> Route/0.0.0.0/0
> - RouteTable              name:demok8scluster.k8s.local
> - CIDR                    0.0.0.0/0
> - InternetGateway         name:demok8scluster.k8s.local

> Route/::/0
> - RouteTable              name:demok8scluster.k8s.local
> - IPv6CIDR                ::/0
> - InternetGateway         name:demok8scluster.k8s.local

> RouteTable/demok8scluster.k8s.local
> - VPC                     name:demok8scluster.k8s.local
> - Shared                  false
> - Tags                    {Name: demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, kubernetes.io/kops/role: public}

> RouteTableAssociation/us-east-1a.demok8scluster.k8s.local
> - RouteTable              name:demok8scluster.k8s.local
> - Subnet                  name:us-east-1a.demok8scluster.k8s.local

> SQS/demok8scluster-k8s-local-nth
> - MessageRetentionPeriod  300
> - Tags                    {Name: demok8scluster-k8s-local-nth, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

Secret/admin

Secret/kube

Secret/kube-proxy

Secret/kubelet

Secret/system:controller_manager

Secret/system:dns

Secret/system:logging

Secret/system:monitoring

Secret/system:scheduler

> SecurityGroup/api-elb.demok8scluster.k8s.local
> - Description             Security group for api ELB
> - VPC                     name:demok8scluster.k8s.local
> - RemoveExtraRules        [port=443]
> - Tags                    {Name: api-elb.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroup/masters.demok8scluster.k8s.local
> - Description             Security group for masters
> - VPC                     name:demok8scluster.k8s.local
> - RemoveExtraRules        [port=22, port=443, port=2380, port=2381, port=3988, port=4001, port=4002, port=4789, port=179, port=8443, port=3:4, port=-1]
> - Tags                    {Name: masters.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroup/nodes.demok8scluster.k8s.local
> - Description             Security group for nodes
> - VPC                     name:demok8scluster.k8s.local
> - RemoveExtraRules        [port=22]
> - Tags                    {Name: nodes.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroupRule/from-0.0.0.0/0-ingress-tcp-22to22-masters.demok8scluster.k8s.local
> - SecurityGroup           name:masters.demok8scluster.k8s.local
> - CIDR                    0.0.0.0/0
> - Protocol                tcp
> - FromPort                22
> - ToPort                  22
> - Tags                    {kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: from-0.0.0.0/0-ingress-tcp-22to22-masters.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local}

> SecurityGroupRule/from-0.0.0.0/0-ingress-tcp-22to22-nodes.demok8scluster.k8s.local
> - SecurityGroup           name:nodes.demok8scluster.k8s.local
> - CIDR                    0.0.0.0/0
> - Protocol                tcp
> - FromPort                22
> - ToPort                  22
> - Tags                    {Name: from-0.0.0.0/0-ingress-tcp-22to22-nodes.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroupRule/from-0.0.0.0/0-ingress-tcp-443to443-api-elb.demok8scluster.k8s.local
> - SecurityGroup           name:api-elb.demok8scluster.k8s.local
> - CIDR                    0.0.0.0/0
> - Protocol                tcp
> - FromPort                443
> - ToPort                  443
> - Tags                    {kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: from-0.0.0.0/0-ingress-tcp-443to443-api-elb.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local}

> SecurityGroupRule/from-::/0-ingress-tcp-22to22-masters.demok8scluster.k8s.local
> - SecurityGroup           name:masters.demok8scluster.k8s.local
> - IPv6CIDR                ::/0
> - Protocol                tcp
> - FromPort                22
> - ToPort                  22
> - Tags                    {Name: from-::/0-ingress-tcp-22to22-masters.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroupRule/from-::/0-ingress-tcp-22to22-nodes.demok8scluster.k8s.local
> - SecurityGroup           name:nodes.demok8scluster.k8s.local
> - IPv6CIDR                ::/0
> - Protocol                tcp
> - FromPort                22
> - ToPort                  22
> - Tags                    {kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: from-::/0-ingress-tcp-22to22-nodes.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local}

> SecurityGroupRule/from-::/0-ingress-tcp-443to443-api-elb.demok8scluster.k8s.local
> - SecurityGroup           name:api-elb.demok8scluster.k8s.local
> - IPv6CIDR                ::/0
> - Protocol                tcp
> - FromPort                443
> - ToPort                  443
> - Tags                    {kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: from-::/0-ingress-tcp-443to443-api-elb.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local}

> SecurityGroupRule/from-api-elb.demok8scluster.k8s.local-egress-all-0to0-0.0.0.0/0
> - SecurityGroup           name:api-elb.demok8scluster.k8s.local
> - CIDR                    0.0.0.0/0
> - Egress                  true
> - Tags                    {Name: from-api-elb.demok8scluster.k8s.local-egress-all-0to0-0.0.0.0/0, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroupRule/from-api-elb.demok8scluster.k8s.local-egress-all-0to0-::/0
> - SecurityGroup           name:api-elb.demok8scluster.k8s.local
> - IPv6CIDR                ::/0
> - Egress                  true
> - Tags                    {Name: from-api-elb.demok8scluster.k8s.local-egress-all-0to0-::/0, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroupRule/from-masters.demok8scluster.k8s.local-egress-all-0to0-0.0.0.0/0
> - SecurityGroup           name:masters.demok8scluster.k8s.local
> - CIDR                    0.0.0.0/0
> - Egress                  true
> - Tags                    {Name: from-masters.demok8scluster.k8s.local-egress-all-0to0-0.0.0.0/0, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroupRule/from-masters.demok8scluster.k8s.local-egress-all-0to0-::/0
> - SecurityGroup           name:masters.demok8scluster.k8s.local
> - IPv6CIDR                ::/0
> - Egress                  true
> - Tags                    {kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: from-masters.demok8scluster.k8s.local-egress-all-0to0-::/0, KubernetesCluster: demok8scluster.k8s.local}

> SecurityGroupRule/from-masters.demok8scluster.k8s.local-ingress-all-0to0-masters.demok8scluster.k8s.local
> - SecurityGroup           name:masters.demok8scluster.k8s.local
> - SourceGroup             name:masters.demok8scluster.k8s.local
> - Tags                    {Name: from-masters.demok8scluster.k8s.local-ingress-all-0to0-masters.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroupRule/from-masters.demok8scluster.k8s.local-ingress-all-0to0-nodes.demok8scluster.k8s.local
> - SecurityGroup           name:nodes.demok8scluster.k8s.local
> - SourceGroup             name:masters.demok8scluster.k8s.local
> - Tags                    {KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: from-masters.demok8scluster.k8s.local-ingress-all-0to0-nodes.demok8scluster.k8s.local}

> SecurityGroupRule/from-nodes.demok8scluster.k8s.local-egress-all-0to0-0.0.0.0/0
> - SecurityGroup           name:nodes.demok8scluster.k8s.local
> - CIDR                    0.0.0.0/0
> - Egress                  true
> - Tags                    {Name: from-nodes.demok8scluster.k8s.local-egress-all-0to0-0.0.0.0/0, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroupRule/from-nodes.demok8scluster.k8s.local-egress-all-0to0-::/0
> - SecurityGroup           name:nodes.demok8scluster.k8s.local
> - IPv6CIDR                ::/0
> - Egress                  true
> - Tags                    {Name: from-nodes.demok8scluster.k8s.local-egress-all-0to0-::/0, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroupRule/from-nodes.demok8scluster.k8s.local-ingress-all-0to0-nodes.demok8scluster.k8s.local
> - SecurityGroup           name:nodes.demok8scluster.k8s.local
> - SourceGroup             name:nodes.demok8scluster.k8s.local
> - Tags                    {kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: from-nodes.demok8scluster.k8s.local-ingress-all-0to0-nodes.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local}

> SecurityGroupRule/from-nodes.demok8scluster.k8s.local-ingress-tcp-1to2379-masters.demok8scluster.k8s.local
> - SecurityGroup           name:masters.demok8scluster.k8s.local
> - Protocol                tcp
> - FromPort                1
> - ToPort                  2379
> - SourceGroup             name:nodes.demok8scluster.k8s.local
> - Tags                    {Name: from-nodes.demok8scluster.k8s.local-ingress-tcp-1to2379-masters.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroupRule/from-nodes.demok8scluster.k8s.local-ingress-tcp-2382to4000-masters.demok8scluster.k8s.local
> - SecurityGroup           name:masters.demok8scluster.k8s.local
> - Protocol                tcp
> - FromPort                2382
> - ToPort                  4000
> - SourceGroup             name:nodes.demok8scluster.k8s.local
> - Tags                    {kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: from-nodes.demok8scluster.k8s.local-ingress-tcp-2382to4000-masters.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local}

> SecurityGroupRule/from-nodes.demok8scluster.k8s.local-ingress-tcp-4003to65535-masters.demok8scluster.k8s.local
> - SecurityGroup           name:masters.demok8scluster.k8s.local
> - Protocol                tcp
> - FromPort                4003
> - ToPort                  65535
> - SourceGroup             name:nodes.demok8scluster.k8s.local
> - Tags                    {kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: from-nodes.demok8scluster.k8s.local-ingress-tcp-4003to65535-masters.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local}

> SecurityGroupRule/from-nodes.demok8scluster.k8s.local-ingress-udp-1to65535-masters.demok8scluster.k8s.local
> - SecurityGroup           name:masters.demok8scluster.k8s.local
> - Protocol                udp
> - FromPort                1
> - ToPort                  65535
> - SourceGroup             name:nodes.demok8scluster.k8s.local
> - Tags                    {Name: from-nodes.demok8scluster.k8s.local-ingress-udp-1to65535-masters.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}

> SecurityGroupRule/https-elb-to-master
> - SecurityGroup           name:masters.demok8scluster.k8s.local
> - Protocol                tcp
> - FromPort                443
> - ToPort                  443
> - SourceGroup             name:api-elb.demok8scluster.k8s.local

> SecurityGroupRule/icmp-pmtu-api-elb-0.0.0.0/0
> - SecurityGroup           name:api-elb.demok8scluster.k8s.local
> - CIDR                    0.0.0.0/0
> - Protocol                icmp
> - FromPort                3
> - ToPort                  4

> SecurityGroupRule/icmp-pmtu-cp-to-elb
> - SecurityGroup           name:api-elb.demok8scluster.k8s.local
> - Protocol                icmp
> - FromPort                3
> - ToPort                  4
> - SourceGroup             name:masters.demok8scluster.k8s.local

> SecurityGroupRule/icmp-pmtu-elb-to-cp
> - SecurityGroup           name:masters.demok8scluster.k8s.local
> - Protocol                icmp
> - FromPort                3
> - ToPort                  4
> - SourceGroup             name:api-elb.demok8scluster.k8s.local

> SecurityGroupRule/icmpv6-pmtu-api-elb-::/0
> - SecurityGroup           name:api-elb.demok8scluster.k8s.local
> - IPv6CIDR                ::/0
> - Protocol                icmpv6
> - FromPort                -1
> - ToPort                  -1

> SecurityGroupRule/kops-controller-elb-to-cp
> - SecurityGroup           name:masters.demok8scluster.k8s.local
> - Protocol                tcp
> - FromPort                3988
> - ToPort                  3988
> - SourceGroup             name:api-elb.demok8scluster.k8s.local

> SecurityGroupRule/node-to-elb
> - SecurityGroup           name:api-elb.demok8scluster.k8s.local
> - SourceGroup             name:nodes.demok8scluster.k8s.local

> Subnet/us-east-1a.demok8scluster.k8s.local
> - ShortName               us-east-1a
> - VPC                     name:demok8scluster.k8s.local
> - AvailabilityZone        us-east-1a
> - CIDR                    172.20.0.0/16
> - ResourceBasedNaming     true
> - AssignIPv6AddressOnCreation     false
> - Shared                  false
> - Tags                    {Name: us-east-1a.demok8scluster.k8s.local, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, SubnetType: Public, kubernetes.io/role/elb: 1, kubernetes.io/role/internal-elb: 1}

> TargetGroup/kops-controller-demok8scl-aprcdq
> - VPC                     name:demok8scluster.k8s.local
> - Tags                    {Name: kops-controller-demok8scl-aprcdq, KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned}
> - Port                    3988
> - Protocol                TCP
> - Shared                  false
> - Attributes              {deregistration_delay.timeout_seconds: 30, deregistration_delay.connection_termination.enabled: true}
> - Interval                10
> - HealthyThreshold        2
> - UnhealthyThreshold      2

> TargetGroup/tcp-demok8scluster-k8s-lo-aoh168
> - VPC                     name:demok8scluster.k8s.local
> - Tags                    {KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: tcp-demok8scluster-k8s-lo-aoh168}
> - Port                    443
> - Protocol                TCP
> - Shared                  false
> - Attributes              {deregistration_delay.connection_termination.enabled: true, deregistration_delay.timeout_seconds: 30}
> - Interval                10
> - HealthyThreshold        2
> - UnhealthyThreshold      2

> VPC/demok8scluster.k8s.local
> - CIDR                    172.20.0.0/16
> - AmazonIPv6              true
> - EnableDNSHostnames      true
> - EnableDNSSupport        true
> - Shared                  false
> - Tags                    {KubernetesCluster: demok8scluster.k8s.local, kubernetes.io/cluster/demok8scluster.k8s.local: owned, Name: demok8scluster.k8s.local}

> VPCAmazonIPv6CIDRBlock/AmazonIPv6
> - VPC                     name:demok8scluster.k8s.local
> - Shared                  false

> VPCDHCPOptionsAssociation/demok8scluster.k8s.local
> - VPC                     name:demok8scluster.k8s.local
> - DHCPOptions             name:demok8scluster.k8s.local

> WarmPool/control-plane-us-east-1a.masters.demok8scluster.k8s.local
> - Enabled                 false
> - MinSize                 0
> - AutoscalingGroup        name:control-plane-us-east-1a.masters.demok8scluster.k8s.local id:control-plane-us-east-1a.masters.demok8scluster.k8s.local

> WarmPool/nodes-us-east-1a.demok8scluster.k8s.local
> - Enabled                 false
> - MinSize                 0
> - AutoscalingGroup        name:nodes-us-east-1a.demok8scluster.k8s.local id:nodes-us-east-1a.demok8scluster.k8s.local

Must specify --yes to apply changes

Cluster configuration has been created.

Suggestions:
 * list clusters with: kops get cluster
 * edit this cluster with: kops edit cluster demok8scluster.k8s.local
 * edit your node instance group: kops edit ig --name=demok8scluster.k8s.local nodes-us-east-1a
 * edit your control-plane instance group: kops edit ig --name=demok8scluster.k8s.local control-plane-us-east-1a

Finally configure your cluster with: kops update cluster --name demok8scluster.k8s.local --yes --admin