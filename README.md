#   Configuring a cgroup driver
    Both the container runtime and the kubelet have a property called "cgroup driver", which is important for the management of cgroups on Linux machines.
    Warning:
    - Matching the container runtime and kubelet cgroup drivers is required or otherwise the kubelet process will fail.
link: https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/
#   br_netfilter
The br_netfilter module is required to enable transparent masquerading and to facilitate Virtual Extensible LAN (VxLAN) traffic for communication between Kubernetes pods across the cluster nodes. Therefore, you must make sure the br_netfilter module is installed on all master and all worker nodes before you change the settings of system parameters. Perform the following steps on all the master and worker nodes to set the system parameters.
link: https://docs.microfocus.com/doc/Data_Center_Automation/2019.11/SetSystemParameters
#    set bridge-nf-call-iptables

Most CNIs rely on iptables rules for at least some of their packet processing, and because they handle the container network, they need to handle bridged packets. If bridged packets aren’t sent through iptables, they aren’t processed as expected by the CNI.
link: https://unix.stackexchange.com/questions/720105/what-is-the-net-bridge-bridge-nf-call-iptables-kernel-parameter