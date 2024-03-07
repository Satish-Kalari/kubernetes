# Commands to use helm

helm install <chart-name> <release-name>
    example: helm install nginx . 

helm list or helm ls # list all the releases

helm upgrade <release-name> <chart-name> # upgrade the release
    example: helm upgrade nginx .

helm upgrade nginx --set deployment.replicas=5 # upgrade the release with new values

helm history <release-name> # history of the release
    example: helm history nginx

helm rollback <release-name> <revision-number> # rollback the release
    example: helm rollback nginx 1

helm show values <chart-name> # show the values of the chart
    example: helm show values . # show the values of the chart
             helm show values nginx # show the values of the nginx chart

helm install nginx --set replicaCount=2 # setting the values vis command line

  

helm status <release-name> # status of the release
helm get values <release-name> # get the values of the release

helm uninstall <release-name> # uninstall the release
helm show chart <chart-name> # show the chart

q: what is chart-name
a: chart-name is the name of the chart which is used to install the release

q: what is release-name
a: release-name is the name of the release which is used to install the chart

# q; setting the values vis command line
# a: helm install nginx . --set replicaCount=2