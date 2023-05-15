## minikube install for linux
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
```
```
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

## for mac
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64
sudo install minikube-darwin-amd64 /usr/local/bin/minikube


```
### create pod using kubectl run 
```
akash@sky:~/Desktop/k8s_code$ kubectl run myprpod --image aakashgaur57/xyz --port 80 --dry-run=client -o yaml 
apiVersion: v1
kind: Pod
metadata:
  creationTimestamp: null
  labels:
    run: myprpod
  name: myprpod
spec:
  containers:
  - image: aakashgaur57/xyz
    name: myprpod
    ports:
    - containerPort: 80
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}
```

```
akash@sky:~$ kubectl get po
NAME    READY   STATUS    RESTARTS      AGE
akpod   1/1     Running   1 (39m ago)   10h
akash@sky:~$ kubectl get po -o wide
NAME    READY   STATUS    RESTARTS      AGE   IP              NODE       NOMINATED NODE   READINESS GATES
akpod   1/1     Running   1 (39m ago)   10h   10.244.120.96   minikube   <none>           <none>


```

### type of secrets 
```
  docker-registry   Create a secret for use with a Docker registry
  generic           Create a secret from a local file, directory, or literal value
  tls               Create a TLS secret

```
### create docker-registry secrets  --dry-run
````
akash@sky:~/Desktop/k8s_code$ kubectl create secret docker-registry my-cred --docker-server=docker.io --docker-username=aakashgaur57 --docker-password="xyz@" --dry-run=client -o yaml 
apiVersion: v1
data:
  .dockerconfigjson: eyJhdXRocyI6eyJkb2NrZXIuaW8iOnsidXNlcm5hbWUiOiJhYWthc2hnYXVyNTciLCJwYXNzd29yZCI6Inh5ekAiLCJhdXRoIjoiWVdGcllYTm9aMkYxY2pVM09uaDVla0E9In19fQ==
kind: Secret
metadata:
  creationTimestamp: null
  name: my-cred
type: kubernetes.io/dockerconfigjson
````
### to create a yaml file of secret
```
kubectl create secret docker-registry my-cred --docker-server=docker.io --docker-username=aakashgaur57 --docker-password="xyz@" --dry-run=client -o yaml >my-cred.yml
```
### run yaml of secret 
```
akash@sky:~/Desktop/k8s_code$kubectl apply -f my-cred.yml
akash@sky:~/Desktop/k8s_code$ kubectl get secrets 
NAME      TYPE                             DATA   AGE
my-cred   kubernetes.io/dockerconfigjson   1      7h58m
```
### 15may history
```
 1939  kubectl get nodes 
 1941  kubectl get po
 1942  kubectl get no
 1943  kubectl api-resources 
 akash@sky:~/Desktop/k8s_code$ kubectl api-resources 
NAME                              SHORTNAMES   APIVERSION                             NAMESPACED   KIND
bindings                                       v1                                     true         Binding
componentstatuses                 cs           v1                                     false        ComponentStatus
configmaps                        cm           v1                                     true         ConfigMap
endpoints                         ep           v1                                     true         Endpoints
events                            ev           v1                                     true         Event
limitranges                       limits       v1                                     true         LimitRange
namespaces                        ns           v1                                     false        Namespace
nodes                             no           v1                                     false        Node
persistentvolumeclaims            pvc          v1                                     true         PersistentVolumeClaim
persistentvolumes                 pv           v1                                     false        PersistentVolume
pods                              po           v1                                     true         Pod
podtemplates                                   v1                                     true         PodTemplate
replicationcontrollers            rc           v1                                     true         ReplicationController
resourcequotas                    quota        v1                                     true         ResourceQuota
secrets                                        v1                                     true         Secret

 
 1945  kubectl run mypo --image httpd --port 80 --dry-run=client -o yaml
 1946  kubectl run mypo --image httpd --port 80 --dry-run=client -o yaml >newpod.yml
 1949  kubectl describe po akpod 
 1953  kubectl get namespaces
 
 akash@sky:~/Desktop/k8s_code$ kubectl get namespaces
NAME                   STATUS   AGE
default                Active   2d14h
kube-node-lease        Active   2d14h
kube-public            Active   2d14h
kube-system            Active   2d14h

 1954  kubectl get pods -n kube-system 
 akash@sky:~/Desktop/k8s_code$  kubectl get pods -n kube-system 
NAME                                      READY   STATUS    RESTARTS        AGE
calico-kube-controllers-7bdbfc669-gvmk7   1/1     Running   3 (6h59m ago)   2d14h
calico-node-kgfdk                         1/1     Running   1 (6h59m ago)   11h
calico-node-nhs5f                         1/1     Running   3 (6h59m ago)   2d14h
coredns-787d4945fb-nc4jw                  1/1     Running   3 (6h59m ago)   2d14h
etcd-minikube                             1/1     Running   3 (6h59m ago)   2d14h
kube-apiserver-minikube                   1/1     Running   3 (67m ago)     2d14h
kube-controller-manager-minikube          1/1     Running   3 (6h59m ago)   2d14h
kube-proxy-4xhmg                          1/1     Running   3 (6h59m ago)   2d14h
kube-proxy-n6f8w                          1/1     Running   1 (6h59m ago)   11h
kube-scheduler-minikube                   1/1     Running   3 (6h59m ago)   2d14h
storage-provisioner                       1/1     Running   6 (66m ago)     2d14h

 1955  kubectl get pods -n kube-system  -o wide
 1956  kubectl get  po --all-namespaces 
 akash@sky:~/Desktop/k8s_code$ kubectl get  po --all-namespaces 
NAMESPACE              NAME                                        READY   STATUS      RESTARTS        AGE
default                akpod                                       1/1     Running     1 (67m ago)     11h
kube-system            calico-node-nhs5f                           1/1     Running     3 (6h59m ago)   2d14h
kube-system            coredns-787d4945fb-nc4jw                    1/1     Running     3 (6h59m ago)   2d14h
kube-system            etcd-minikube                               1/1     Running     3 (6h59m ago)   2d14h
kube-system            kube-apiserver-minikube                     1/1     Running     3 (67m ago)     2d14h
kube-system            kube-controller-manager-minikube            1/1     Running     3 (6h59m ago)   2d14h
kube-system            kube-proxy-4xhmg                            1/1     Running     3 (6h59m ago)   2d14h
kube-system            kube-proxy-n6f8w                            1/1     Running     1 (6h59m ago)   11h
kube-system            kube-scheduler-minikube                     1/1     Running     3 (6h59m ago)   2d14h
kube-system            storage-provisioner                         1/1     Running     6 (66m ago)     2d14h

 
 1957  kubectl get  po -A
 1959  docker ps
 1960  docker exec -it minikube bash
 1965  kubectl get ns
 1966  kubectl get po -n kube-system 
 1967  kubectl get  node
 1968  kubectl get po -n kube-system -o wide
 1969  kubectl get po
 1970  kubectl get po -o wide
```
