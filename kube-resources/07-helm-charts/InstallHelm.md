# Install Helm
once cluster is created 
Connect to workstation via putty

***install helm?*** (done via workstation.sh from /kubernetes/eksctl/woekstation.sh)
- curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
- chmod 700 get_helm.sh
- ./get_helm.sh

Verify the installation
- helm version


# installing ebs helm repo
- helm repo add aws-ebs-csi-driver https://kubernetes-sigs.github.io/aws-ebs-csi-driver
- helm repo update
- helm upgrade --install aws-ebs-csi-driver -namespace kube-system aws-ebs-csi-driver/aws-ebs-csi-driver

to uninstall
- helm uninstall aws-ebs-csi-driver -n kube-system

# installing jenkins helm repo
- helm repo add jenkins https://charts.jenkins.io
- helm repo update
- helm install jenkins jenkins/jenkins


# what are helm charts?
Helm charts are a collection of files that describe a related set of Kubernetes resources. A single chart might be used to deploy something simple, like a memcached pod, or something complex, like a full web app stack with HTTP servers, databases, caches, and so on.
