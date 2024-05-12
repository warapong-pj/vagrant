# kubernetes

### step to deploy
- vagrant up

### how to access to instance
- vagrant ssh

### step to initial cluster and setup kubeconfig
1. export MASTER_NODE_IP=xx.xx.xx.xx && export K8S_POD_NETWORK_CIDR=10.244.0.0/16
2. sudo kubeadm init --apiserver-advertise-address=$MASTER_NODE_IP --pod-network-cidr=$K8S_POD_NETWORK_CIDR --control-plane-endpoint $MASTER_NODE_IP
3. mkdir -p $HOME/.kube
4. sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
5. sudo chown $(id -u):$(id -g) $HOME/.kube/config
