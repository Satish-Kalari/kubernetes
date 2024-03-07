setting environment for stateful sets
1. install drivers
   in workstation vis aupper putty
- helm repo add aws-ebs-csi-driver https://kubernetes-sigs.github.io/aws-ebs-csi-driver
- helm repo update
- helm upgrade --install aws-ebs-csi-driver -namespace kube-system aws-ebs-csi-driver/aws-ebs-csi-driver

2. provide iam role access to the nodes/ec2 instances
- go to node instance in aws console
- go to security tab
- click on the role
- click on add permission
- search for ebs
- select ebs driver policy and attach policy
- add permission

3. install storage class
    git clone /kube-resource/05-storage/ebs-sc.yaml    
- kubectl apply -f ebs-sc.yaml