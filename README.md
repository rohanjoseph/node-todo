Node application application has been dockeriezed as well as the mongodb which acted as a datasbase source to the node application.

Folder's containing kuberbnetes deployment, configmaps and services are pushed into the repository.

1)mongodb

2)node-k8s

3)nginx

4)namespaces-k8s

follow the below step for deploying the kubernetes managed app.

1) Please create the namespace by typing the below comamnd in you terminal

kubectl create -f namespace_stellar.yml

note: the value can be changed 

2)Please create the deployment by typing the below command for each given folder for example

kubectl create -f deployment-nginx -n {namespace}

3)Please create the service by typing the below command for each given folder for example

kubectl create -f service.yml -n {namespace}

4)The kubernetes cluster have been configured for the variable so configmaps has been introduced. Please create configmaps for nginx and node-app

i)please go to the node-k8s directory and type the below command to create the configmaps

kubectl create configmap database-config --from-file=database.js -n {namespace}

ii)please go to the nginx directory and type the below command.

kubectl create -f config-map.yml -n {namespace}

5)Persistant volume and Persistant volume claim

please create pv and pvc by entering into the mongo direcoty and typing the below command

kubectl create -f mongo-pv.yml -n {namespace}

kubectl create -f mongo-pvc.yml -n {namespace}

note: please provide the ebs volume id and create the pv.
