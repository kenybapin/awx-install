# awx-install
Ready to use AWX set up

# AWX for Server

### Requirements
- vagrant
- ansible 2.9


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
URL: http://192.168.233.200
```
<br>
<br>

# AWX with Kubernetes (single node)

### Requirements
- vagrant
- ansible 2.9

### Features

-  Flannel Container Networking (CNI)
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
URL: http://192.168.233.200
```
