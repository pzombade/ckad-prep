Shortcuts:
```
alias k=kubectl
export do="--dry-run=client -o yaml"
k config set-context --current --namespace=core-banking
```
Examples:
```
k run nginx --image nginx $do > n2.yaml
```

```
k set image pod/nginx nginx=nginx:1.7
k taint node controlplane k=v:NoSchedule
kubectl annotate deployment/nginx-deployment kubernetes.io/change-cause="image updated to 1.16.1"
```

Create a pod that will be placed on node controlplane. Use nodeSelector and tolerations.
```
nodeSelector:
  kubernetes.io/hostName: controlplane
```


Expose run and expose nginx image on port 80. Hit this image with busybox on the nginx cluster ip.
```
k run nginx --image nginx --port 80 --expose
k run busybox --image busybox --restart Never --rm -it -- wget -O- <POD_CLUSTER_IP>:80 exit
```
