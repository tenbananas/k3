# k3s
## Quick deployment
```bash
curl -sfL https://get.k3s.io | sh -

# get token
cat /var/lib/rancher/k3s/server/node-token
```

```bash
mkdir ~/.kube
cp /etc/rancher/k3s/k3s.yaml ~/.kube/config 
chmod 600 ~/.kube/config
export KUBECONFIG=~/.kube/config
```

Check
```bash
kubectl get nodes
kubectl cluster-info
```


Add clients
```bash
export K3S_URL="https://192.168.188.81:6443"
export K3S_TOKEN="K105c549fa1cf342f7503c985a2dd9f45d10656e3214e4dad10baccda5092f9f64e::server:abdfd120ee414e6ed651355ea8ce3ee0"
curl -sfL https://get.k3s.io | sh -
```

Check
```bash
kubectl get nodes
```

Small deployment
```bash
kubectl create deployment  nginx-app --image nginx --replicas 2
kubectl get deployment nginx-app
kubectl get pods
kubectl expose deployment nginx-app --type NodePort --port 80

kubectl get svc nginx-app

curl http://<ip>


``

Uninstall
```bash
/usr/local/bin/k3s-uninstall.sh
/usr/local/bin/k3s-agent-uninstall.sh
```
