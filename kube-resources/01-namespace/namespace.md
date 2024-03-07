https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/

# Namespaces
In Kubernetes, namespaces provides a mechanism for isolating groups of resources within a single cluster. 
# When to Use Multiple Namespaces
Namespaces are intended for use in environments with many users spread across multiple teams, or projects.

# Initial namespaces
Kubernetes starts with four initial namespaces:

# default
Kubernetes includes this namespace so that you can start using your new cluster without first creating a namespace.
# kube-node-lease
This namespace holds Lease objects associated with each node. Node leases allow the kubelet to send heartbeats so that the control plane can detect node failure.
# kube-public
This namespace is readable by all clients (including those not authenticated). This namespace is mostly reserved for cluster usage, in case that some resources should be visible and readable publicly throughout the whole cluster. The public aspect of this namespace is only a convention, not a requirement.
# kube-system
The namespace for objects created by the Kubernetes system

