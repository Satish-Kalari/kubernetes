# Role-Based Access Control. [RBAC] #
It is a security model used to manage access to resources within a system. RBAC provides a way to control what actions users can perform and what data they can access based on their assigned roles.

***How to find if resource is namespaced or cluster level?***
kubectl api-resources | grep nodes
    if the resource is namespaced [true], it will have a namespace column. If the resource is cluster level, it will not have a namespace column.

* Role and RoleBinding is at namespace level. It is used to control access to resources within a namespace, such as pods, services, and deployments.

* clusterRole and clusterRoleBinding is at cluster level. It is used to control access to resources within a cluster, such as nodes, namespaces, and persistent volumes.

# 1. creating iam user [In-aws-console]
1.create a new user, name ramesh
2.select attach policies directly
3.select create policy
4.search for eks
5.select access level based on the requirement
6.under resources, select specific and 
    - Click on add ARN
    - Resource region Ex: us-east-1
    - Resource cluster name Ex: roboshop-cluster
    - Resource ARN Ex: arn:aws:eks:us-east-1:123456789012:cluster/roboshop-cluster
    - click on next
7.Policy name Ex: eks-admin
8.click on create policy
9.select the policy eks-admin and click on next
10.click on create user

# 2. Creating role and rolebinding [worker-level.yaml]
cd admin
worker-level.yaml
contain role, rolebinding and clusterRole, ClusterRolebinding for the user ramesh

***in workstation ec2 instance via supper putty***
kubectl apply -f worker-level.yaml

if want admin level access, apply admin-level.yaml
-----------------------------------------------------

# 3. EKS intigration with IAM user [aws-auth.yaml]
Need to edit the configmap/aws-auth in kube-system namespace to integrate the IAM user with EKS cluster.

cd aws-auth.yaml
Maping the IAM user with EKS cluster

***in workstation ec2 instance via supper putty***
kubectl apply -f aws-auth.yaml

***to check the configmap/aws-auth in kube-system namespace***
kubectl get -n kube-system configmap/aws-auth -o yaml 
or
kubectl get configmap aws-auth -n kube-system -o yaml

## To check id the role and rolebinding is created successfully:
1.create an ec2 instance 
2.create user security credentials in aws console
3.access the ec2 instance via putty
4.aws configure [aws-configure]
    [select region that we created in Resource region Ex: us-east-1 in # creating iam user in aws console and provide the access key and secret key]
5.aws sts get-caller-identity # to check the user
6.aws eks update-kubeconfig --region us-east-1 --name roboshop-cluster # to update the kubeconfig
7.cat ~/.kube/config # to check the user and role

-kubectl install-
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.18.0/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
kubectl version --client
kubectl get nodes




# q: cluster level resources?
 a:  ["nodes", "namespaces", "componentstatuses", "customresourcedefinitions", "storageclasses", "csidrivers", "csinodes", "tokenreviews", "selfsubjectaccessreviews", "selfsubjectrulesreviews", "subjectaccessreviews", "horizontalpodautoscalers", "podsecuritypolicies", "poddisruptionbudgets", "priorityclasses", "runtimeclasses", "csidrivers", "csinodes", "storageclasses

# q: namespace level resources?
a: ["pods", "pods/log", "services", "deployments", "replicasets", "statefulsets", "configmaps", "secrets", "ingresses", "persistentvolumeclaims", "persistentvolumes", "jobs", "cronjobs"]
