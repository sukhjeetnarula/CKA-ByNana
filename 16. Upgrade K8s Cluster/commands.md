### Upgrade control plane node

#### Check apt-get version
sudo apt-get --version

#### For apt-get version gt 1.1
sudo apt-get update
sudo apt-get install -y --allow-change-held-packages kubeadm=1.22.0-00

#### Get upgrade preview
sudo kubeadm upgrade plan

#### Upgrade cluster 
sudo kubeadm upgrade apply v1.22.0

#### Drain node
kubectl drain master --ignore-daemonsets

#### Upgrade kubelet & kubectl 
sudo apt-get update
sudo apt-get install -y --allow-change-held-packages kubelet=1.22.0-00 kubectl=1.22.0-00

#### Restart kubelet
sudo systemctl daemon-reload
sudo systemctl restart kubelet

#### Uncordon node
kubectl uncordon master


### Upgrade worker node
sudo apt-get update && \
sudo apt-get install -y --allow-change-held-packages kubeadm=1.22.x-00

sudo kubeadm upgrade node

kubectl drain worker1 --ignore-daemonsets --force

sudo apt-get update
sudo apt-get install -y --allow-change-held-packages kubelet=1.22.x-00 kubectl=1.22.x-00

sudo systemctl daemon-reload
sudo systemctl restart kubelet

kubectl uncordon worker1