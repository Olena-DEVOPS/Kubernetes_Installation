PART 1. MASTER NODE


apt-get update

apt-get install docker.io -y

service docker restart

curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -

echo "deb http://apt.kubernetes.io/ kubernetes-xenial main" >/etc/apt/sources.list.d/kubernetes.list

apt-get update

apt install kubeadm=1.20.0-00 kubectl=1.20.0-00 kubelet=1.20.0-00 -y

kubeadm init --pod-network-cidr=10.244.0.0/16

mkdir -p $HOME/.kube

sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config

sudo chown $(id -u):$(id -g) $HOME/.kube/config

kubectl apply -f https://raw.githubusercontent.com/flannel-io/flannel/master/Documentation/kube-flannel.yml


NOTE !
1. Now run this command to generate a token in master node and copy this generated token first::  kubeadm generate token   
2. Now run this to create a join token command (put your token in place of hp9b0k.1g9tqz8vkf78ucwf)::  kubeadm token create hp9b0k.1g9tqz8vkf78ucwf --print-join-command  
3. Now copy the join token command and run it in your worker node. After running it check your worker node is joined or not in your master node by::  kubectl get nodes



PART 2. WORKER NODE

apt-get update

apt-get install docker.io -y

service docker restart

curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -

echo "deb http://apt.kubernetes.io/ kubernetes-xenial main" >/etc/apt/sources.list.d/kubernetes.list

apt-get update

apt install kubeadm=1.20.0-00 kubectl=1.20.0-00 kubelet=1.20.0-00 -y
