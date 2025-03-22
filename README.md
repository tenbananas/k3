# k3s
## Quick deployment
```bash
curl -sfL https://get.k3s.io | sh -

# get token
cat /var/lib/rancher/k3s/server/node-token
```

Add clients
```bash
export K3S_URL="https://192.168.188.81:6443"
export K3S_TOKEN="K1090ab8da53e6e9bf9ef134531f8218734b891d158982f521e71c9f24da5f655fd::server:8232f4702f7b0fa21631c4faaaebf2de"
curl -sfL https://get.k3s.io | sh -
```

Check
```bash
kubectl get nodes
```

Uninstall
```bash
/usr/local/bin/k3s-uninstall.sh
/usr/local/bin/k3s-agent-uninstall.sh
```
