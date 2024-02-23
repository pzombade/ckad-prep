Shortcuts:
```
alias k=kubectl
export do="--dry-run=client -o yaml"
k config set-context --current --namespace=core-banking
```
Exampels:
```
k run nginx --image nginx do > n2.yaml
```

```
k set image pod/nginx nginx=nginx:1.7
k taint node controlplane k=v:NoSchedule
kubectl annotate deployment/nginx-deployment kubernetes.io/change-cause="image updated to 1.16.1"
```
