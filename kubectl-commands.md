# kubectl create commands
- kubectl create -f <file>
- kubectl create -f <directory>
- kubectl create -f <url>

# kubectl apply commands
- kubectl apply -f <file>
- kubectl apply -f <directory>
- kubectl apply -f <url>

# kubectl get commands
- kubectl get pods
- kubectl get pods -o wide 
- kubectl get pods -o yaml
- kubectl get pods -o json
- kubectl get pods -o custom-columns
- kubectl get pods -o custom-columns=POD_NAME:.metadata.name,POD_IP:.status.podIP

# kubectl login commands
- kubectl login
- kubectl login -u <username>
- kubectl login -p <password>
- kubectl login -u <username> -p <password>

# Kubectl container login commands
- kubectl exec -it <pod-name> -- /bin/bash 
- kubectl exec -it <pod-name> -- /bin/sh 
- kubectl exec -it <pod-name> -- /bin/sh -c "ls -l"
- kubectl exec -it <pod-name> -- /bin/sh -c "cat /etc/hosts"
- kubectl exec -it <pod-name> -- /bin/sh -c "cat /etc/resolv.conf"
- kubectl exec -it <pod-name> -- /bin/sh -c "cat /etc/hostname"

# kubectl describe commands
- kubectl describe pods <pod-name>
- kubectl describe pods <pod-name> -o wide
- kubectl describe pods <pod-name> -o yaml
- kubectl describe pods <pod-name> -o json
- kubectl describe pods <pod-name> -o custom-columns






