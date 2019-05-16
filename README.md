# kubernetesthursdaypractice
kubectl get nodes
kubectl get pods
kubectl get pods -o wide
kubectl run --image nginx webserver --containerport=80 --hostport=8080
kubectl run --image mysql:5 mydb --env MYSQL_ROOT_PASSWORD=admin 
kubectl run --image jenkins jenkinsserver --containerport=8080 --hostport=8080
kubectl exec -it mydb bash
kubectl run --image tomcat appserver --containerport=8080 --hostport=8888
kubectl delete servicename
kubectl logs -f podname
------------------->>>>>>>>>>>>>>>>>>>>>><<<<<<<<<<<<<<<<<<<<<<<<<------------------------
apiVersion: v1
kind: Pod
metadata:
  name: apps-pod
  lables:
    app: pod
spec:
  containers:
  - name: webserver
    image: nginx:1.7.9
    command: ['sh', 'ls']
    
-------------------->>>>>>>>>><<<<<<<<<<<<<<<<<<---------------------------
apiVersion: apps/v1
kind: Deployment
metadata:
  name: apps
  lables:
    app: pod
spec:
  replicas: 3
  selector:
    matchlables:
      app: pod
  template:
    metadata:
      name: nameof the template
      lables:
        app: pods
    spec:
      containers:
       - name:
         image:
         command:
         ports:
         
#To apply
kubectl apply -f deployment.yaml --record
#usagecase1:
apiVersion: v1
kind: Pod
metadata: 
  name: app-pod
  lables:
    app: pod
spec:
  containers:
  - name: httpd
    image: httpd
#To deploy the aboe pod
 kubectl create -f filename.yml --record
#To deploy the deployment
 kubectl apply -f filename.yml --record
#To delete a service 
 kubectl delete -f filename.yml
 
apiVersion: v1
kind: Pod
metadata:
  name: myapp-postgre
  lables:
    myapp: postgre
spec:
  containers:
  - name: postgres
    image: postgres
apiVersion: v1
kind: Pod
metadata:
  name: myapp-db
  lables:
    myapp: db
    tier: dbname
spec:
  containers:
  - image: mysql:5
    name: db
    env:
    - name: MYSQL_ROOT_PASSWORD
      value: admin
 apiVersion: v1
 kind: Pod
 metadata: 
   name: myapp-jenkins
   lables: 
     myapp: jenkins
spec:
  containers:
  - name: myjenkins
    image: jenkins
    ports:
    - containerport: 8080
      hostport: 5050
apiVersion: v1
kind: ReplicationController
metadata: 
  name: my-rc-tomcat
  lables:
    my-rc: tomcat
spec: 
  replicas: 3
  template:
    metadata:
      name: app-tomcat
      lables:
        my-rc-tomcat
    spec:
      containers:
      - name: tomcat
        image: tomcat
        ports:
        - containerport: 8080
          hostport: 8787
#scaling the replica count to a bigger
kubectl scale --replicas=6 -f filenaem.yml
kubectl scale --replicas=4 -f filename.yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  lables:
    app: nginx
spec:
  replicas: 3
  selector:
    matchlables:
    
  template:
    metadata: 
      name: 
      lables:
    spec:
      containers:
      - name:
        image: 
        ports:
        - containerport:
          hostport:
        env:
        - name: 
          value:

v1 pod replicationcontroller
apps/v1 replicasset and deployment
scale up or down replication controller static content
update replicasset and deployment  dynamic content
kubectl create -f filename
kubectl apply -f filenme --record
kubectl delete -f filenaem --record
kubectl delete service_name
kubectl scale --replicas=6 -f filename.yml --record
kubectl:This is the appication used by the kubernetes and for running the k8s commands
kubeadm:This is used to create the master and the slave nodes in the cluster
   
          
          
         
      

    

