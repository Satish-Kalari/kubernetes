StatefulSet is the workload API object used to manage ***stateful applications.***

Deployment is the workload API object used to ***manage stateless applications.***

deployment is used for stateless applications, 
statefulset is used for stateful applications.


* nodes inside stateful applications should have static names and stable network identities. to communicate with other nodes.

* stateful application should follow ordered create and delete.
    - create forward and delete in reverse order.

* stateful application use headless service to control the network identity of the pods.

Session-59 | DevOps with AWS - 76S 

# Headless service 
- is a service with clusterIP: None. 
- It is used to control the network identity of the pods.

how headless service is used to control the network identity of the pods?
- ***headless service is used to control the network identity of the pods by providing a stable network identity to the pods.***

why headless service is required for stateful applications?
- ***headless service is required for stateful applications to provide a stable network identity to the pods.***