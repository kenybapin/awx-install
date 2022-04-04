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

```
git clone https://github.com/kenybapin/awx-install.git
cd awx-install/awx-vm-deploy/
vagrant up
```
> :warning: Cygwin/WSL1 users, git clone in windows dir (/mnt/c/...)

### Access
```
URL: http://<VM-IP>:80
secret : password (default)
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

```
git clone https://github.com/kenybapin/awx-install.git
cd awx-install/awx-k8s-deploy/
vagrant up
```
> :warning: Cygwin/WSL1 users, git clone in windows dir (/mnt/c/...)
> 
### Access
```
URL: http://<VM-IP>:<Nodeport>
secret: kubectl -n awx get secret awx-admin-password -o go-template='{{range $k,$v := .data}}{{printf "%s: " $k}}{{if not $v}}{{$v}}{{else}}{{$v | base64decode}}{{end}}{{"\n"}}{{end}}'
```
