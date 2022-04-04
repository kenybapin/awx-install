# awx-install
Ready to use AWX set up

# AWX for Server

### Requirements
- vagrant
- ansible 2.9
- VM: 1 VCPU / 2GB RAM (minimal)

### Features
-  Docker
-  Ansible
-  AWX

### Setup
```
git clone https://github.com/kenybapin/awx-install.git
cd awx-install/awx-vm-deploy/
vagrant up
```
> :warning: Cygwin/WSL1 users, git clone in windows dir (/mnt/c/...)

### Access
```
URL: http://<VM-IP>:80
secret: password (default)
```
<br>
<br>

# AWX with Kubernetes (single node)

### Requirements
- vagrant
- ansible 2.9
- VM: 4 VCPU / 8GB RAM (minimal)

### Features

-  Flannel CNI
-  Persistent Volume (Local storage)
-  AWX Pods

### Setup
```
git clone https://github.com/kenybapin/awx-install.git
cd awx-install/awx-k8s-deploy/
vagrant up
```
> :warning: Cygwin/WSL1 users, git clone in windows dir (/mnt/c/...)
<br>

Install could take about 15min (depending on your hardware configuration)
```
vagrant@awx:~$ kubectl get pods
NAME                                               READY   STATUS    RESTARTS   AGE
awx-85966564f4-zsxrm                               4/4     Running   0          19m
awx-operator-controller-manager-5d9949568d-pp9bj   2/2     Running   0          21m
awx-postgres-0                                     1/1     Running   0          20m
vagrant@awx:~$ kubectl get svc
NAME                                              TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
awx-operator-controller-manager-metrics-service   ClusterIP   10.98.104.183    <none>        8443/TCP       21m
awx-postgres                                      ClusterIP   None             <none>        5432/TCP       20m
awx-service                                       NodePort    10.105.181.191   <none>        80:30080/TCP   19m
```

### Access
```
URL: http://<VM-IP>:<Nodeport>
secret: kubectl -n awx get secret awx-admin-password -o jsonpath="{.data.password}" | base64 --decode
```
