# kubernetes

### step to deploy
- vagrant up

### how to access to instance
- vagrant ssh

### step to initial cluster and setup kubeconfig
1. kubeadm init --apiserver-advertise-address=$MASTER_NODE_IP --pod-network-cidr=K8S_POD_NETWORK_CIDR --control-plane-endpoint $MASTER_NODE_IP
2. mkdir -p $HOME/.kube
3. sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
4. sudo chown $(id -u):$(id -g) $HOME/.kube/config
