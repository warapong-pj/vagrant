# kubernetes

### step to deploy
- vagrant up

### how to access to instance
- vagrant ssh

### step to initial cluster and setup kubeconfig
1. sudo kubeadm init --skip-phases=addon/kube-proxy
2. mkdir -p $HOME/.kube
3. sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
4. sudo chown $(id -u):$(id -g) $HOME/.kube/config
5. kubectl taint nodes --all node-role.kubernetes.io/control-plane-
6. helm repo add cilium https://helm.cilium.io/
7. helm install cilium cilium/cilium --version 1.15.8 --namespace kube-system --set kubeProxyReplacement=true --set k8sServiceHost=192.168.1.40 --set k8sServicePort=6443 --set operator.replicas=1
