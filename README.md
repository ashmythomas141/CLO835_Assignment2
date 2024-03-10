# CLO835_Assignment2

### Terraform codes:

- ssh-keygen -f assignment
- Terraform init 
- terraform validate
- terraform plan
- terraform apply

- Copy all the files that are installed to the instance `scp -i assignment init_kind.sh kind.yaml <public IP>:/tmp`
- ssh into the newly created ec2 instance `ssh -i assignment <public ip>`
- `cd /tmp`
- `chmod 777 init_kind.sh`
- Run the installation scrip for kind cluster ``./init_kind.sh`
- Verify the cluster in running ` kubectl get nodes `

 ```
[ec2-user@ip-172-31-7-40 tmp]$ kubectl get nodes
NAME                 STATUS   ROLES    AGE   VERSION
kind-control-plane   Ready    master   43m   v1.19.11
[ec2-user@ip-172-31-7-40 tmp]$ 

```

```
[ec2-user@ip-172-31-7-40 tmp]$ kubectl get all --all-namespaces
NAMESPACE            NAME                                             READY   STATUS    RESTARTS   AGE
kube-system          pod/coredns-f9fd979d6-67zdt                      1/1     Running   0          103m
kube-system          pod/coredns-f9fd979d6-jt4rn                      1/1     Running   0          103m
kube-system          pod/etcd-kind-control-plane                      1/1     Running   0          103m
kube-system          pod/kindnet-wdxns                                1/1     Running   0          103m
kube-system          pod/kube-apiserver-kind-control-plane            1/1     Running   0          103m
kube-system          pod/kube-controller-manager-kind-control-plane   1/1     Running   0          103m
kube-system          pod/kube-proxy-2hbxz                             1/1     Running   0          103m
kube-system          pod/kube-scheduler-kind-control-plane            1/1     Running   0          103m
local-path-storage   pod/local-path-provisioner-547f784dff-rgb5r      1/1     Running   0          103m

NAMESPACE     NAME                 TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)                  AGE
default       service/kubernetes   ClusterIP   10.96.0.1    <none>        443/TCP                  103m
kube-system   service/kube-dns     ClusterIP   10.96.0.10   <none>        53/UDP,53/TCP,9153/TCP   103m

NAMESPACE     NAME                        DESIRED   CURRENT   READY   UP-TO-DATE   AVAILABLE   NODE SELECTOR            AGE
kube-system   daemonset.apps/kindnet      1         1         1       1            1           <none>                   103m
kube-system   daemonset.apps/kube-proxy   1         1         1       1            1           kubernetes.io/os=linux   103m

NAMESPACE            NAME                                     READY   UP-TO-DATE   AVAILABLE   AGE
kube-system          deployment.apps/coredns                  2/2     2            2           103m
local-path-storage   deployment.apps/local-path-provisioner   1/1     1            1           103m

NAMESPACE            NAME                                                DESIRED   CURRENT   READY   AGE
kube-system          replicaset.apps/coredns-f9fd979d6                   2         2         2       103m
local-path-storage   replicaset.apps/local-path-provisioner-547f784dff   1         1         1       103m

```

