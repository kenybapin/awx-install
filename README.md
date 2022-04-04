# awx-install
Ready to use AWX set up

# Deploying on Server

## Requirements
- vagrant
- ansible 2.9

## Setup
```
git clone <url>
cd <git_repo><folder>
vagrant up
```

# Deploying on Kubernetes

## Requirements

#### 1) Kubernetes
#### 2) CNI installed
#### 3) Persistent Volume
###### K8s Single node (local storage)
  ```
  get https://raw.githubusercontent.com/rancher/local-path-provisioner/v0.0.19/deploy/local-path-storage.yaml -O /root/local-path-storage.yaml
  sed -i "s#/opt/local-path-provisioner#/mnt/local-storage#g" /root/local-path-storage.yaml
  kubectl apply -f /root/local-path-storage.yaml
  ```
###### K8s multi-node (shared storage) TO DO ...
