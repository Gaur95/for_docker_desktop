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
