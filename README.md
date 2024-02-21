Shortcuts:
```
alias k=kubectl
export do="--dry-run=client -o yaml"
k config set-context --current --namespace=core-banking
```
Exampes:
```
k run nginx --image nginx do > n2.yaml
```

```
k set image pod/nginx nginx=nginx:1.7.
```
