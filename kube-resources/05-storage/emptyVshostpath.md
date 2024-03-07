emptyDir vs hostPath
emptyDir is a simple volume type that is created on the node's disk and exists as long as the pod is running on that node. It is initially empty and can be used to share files between containers running in the same pod. It is also used to store temporary data that is not needed between pod restarts. emptyDir volumes are deleted when the pod is removed from the node.
hostPath is used to mount a file or directory from the host node's filesystem into your pod. It is not recommended to use hostPath for production workloads as it is not portable across different nodes. It is useful for testing and development purposes.
# emptyDir: act as a sidecar and collect logs from the main container. 
    The main container writes logs to a directory in the emptyDir volume, and the sidecar container reads the logs and sends them to a centralized logging system.
# hostPath: ships all worker nodes logs to a centralized logging system. 
    The hostPath volume is used to mount the /var/log directory from the host node's filesystem into the pod. The sidecar container reads the logs from the /var/log directory and sends them to a centralized logging system.