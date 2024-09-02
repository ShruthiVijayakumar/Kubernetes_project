# Kubernetes_project
it is just a project with deployment of a wep application with database in kubernetes cluster. 

the terminal of the kubectl commands used: 

PS C:\Users\shrut> minikube start --driver docker
* minikube v1.33.1 on Microsoft Windows 11 Home Single Language 10.0.22631.4037 Build 22631.4037
* Using the docker driver based on user configuration
* Using Docker Desktop driver with root privileges
* Starting "minikube" primary control-plane node in "minikube" cluster
* Pulling base image v0.0.44 ...
* Downloading Kubernetes v1.30.0 preload ...
    > preloaded-images-k8s-v18-v1...:  342.90 MiB / 342.90 MiB  100.00% 2.45 Mi
    > gcr.io/k8s-minikube/kicbase...:  481.58 MiB / 481.58 MiB  100.00% 3.31 Mi
* Creating docker container (CPUs=2, Memory=4000MB) ...
* Preparing Kubernetes v1.30.0 on Docker 26.1.1 ...
  - Generating certificates and keys ...
  - Booting up control plane ...
  - Configuring RBAC rules ...
* Configuring bridge CNI (Container Networking Interface) ...
* Verifying Kubernetes components...
  - Using image gcr.io/k8s-minikube/storage-provisioner:v5
* Enabled addons: storage-provisioner, default-storageclass
* Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default
PS C:\Users\shrut>
PS C:\Users\shrut> minikube nodes
Error: unknown command "nodes" for "minikube"

Did you mean this?
        node

Run 'minikube --help' for usage.
PS C:\Users\shrut> minikube node

X Exiting due to MK_USAGE: Usage: minikube node [add|start|stop|delete|list]

PS C:\Users\shrut> minikube status
minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured

PS C:\Users\shrut> kubectl get node
NAME       STATUS   ROLES           AGE     VERSION
minikube   Ready    control-plane   2m30s   v1.30.0
PS C:\Users\shrut> echo -n mongouser | base64
base64 : The term 'base64' is not recognized as the name of a
cmdlet, function, script file, or operable program. Check the
spelling of the name, or if a path was included, verify that
the path is correct and try again.
At line:1 char:21
+ echo -n mongouser | base64
+                     ~~~~~~
    + CategoryInfo          : ObjectNotFound: (base64:String)
   [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\Users\shrut> kubectl get all
NAME                                    READY   STATUS
    RESTARTS   AGE
pod/mongo-deployment-5cd59c6ff5-bkn7r   1/1     Running
    0          67s
pod/webapp-deployment-bd7557f5c-zr45x   0/1     ContainerCreating   0          38s

NAME                     TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
service/kubernetes       ClusterIP   10.96.0.1        <none>        443/TCP          70m
service/mongo-service    ClusterIP   10.108.177.223   <none>        27017/TCP        67s
service/webapp-service   NodePort    10.98.212.174    <none>        3000:30100/TCP   38s

NAME                                READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/mongo-deployment    1/1     1            1           67s
deployment.apps/webapp-deployment   0/1     1            0           38s

NAME                                          DESIRED   CURRENT   READY   AGE
replicaset.apps/mongo-deployment-5cd59c6ff5   1         1         1       67s
replicaset.apps/webapp-deployment-bd7557f5c   1         1         0       38s
PS C:\Users\shrut> kubectl get all
NAME                                    READY   STATUS    RESTARTS   AGE
pod/mongo-deployment-5cd59c6ff5-bkn7r   1/1     Running   0          4m38s
pod/webapp-deployment-bd7557f5c-zr45x   1/1     Running   0          4m9s

NAME                     TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
service/kubernetes       ClusterIP   10.96.0.1        <none>        443/TCP          73m
service/mongo-service    ClusterIP   10.108.177.223   <none>        27017/TCP        4m38s
service/webapp-service   NodePort    10.98.212.174    <none>        3000:30100/TCP   4m9s

NAME                                READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/mongo-deployment    1/1     1            1           4m38s
deployment.apps/webapp-deployment   1/1     1            1           4m9s

NAME                                          DESIRED   CURRENT   READY   AGE
replicaset.apps/mongo-deployment-5cd59c6ff5   1         1         1       4m38s
replicaset.apps/webapp-deployment-bd7557f5c   1         1         1       4m9s
PS C:\Users\shrut> kubectl get pod
NAME                                READY   STATUS    RESTARTS   AGE
mongo-deployment-5cd59c6ff5-bkn7r   1/1     Running   0          9m20s
webapp-deployment-bd7557f5c-zr45x   1/1     Running   0          8m51s
PS C:\Users\shrut> kubectl get node
NAME       STATUS   ROLES           AGE   VERSION
minikube   Ready    control-plane   79m   v1.30.0
PS C:\Users\shrut> minikube ip
192.168.49.2
PS C:\Users\shrut> minikube ip
192.168.49.2
