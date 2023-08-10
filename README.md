# night_b
### namespaces
```
akash@sky:~$ kubectl get namespaces 
NAME                   STATUS   AGE
ak                     Active   23d
default                Active   33d
ingress-nginx          Active   33d
kube-node-lease        Active   33d
kube-public            Active   33d
kube-system            Active   33d
kubernetes-dashboard   Active   15d
akash@sky:~$ kubectl get  ns
NAME                   STATUS   AGE
ak                     Active   23d
default                Active   33d
ingress-nginx          Active   33d
kube-node-lease        Active   33d
kube-public            Active   33d
kube-system            Active   33d
kubernetes-dashboard   Active   15d
akash@sky:~$ kubectl get pod
NAME   READY   STATUS    RESTARTS      AGE
ak     1/1     Running   1 (10m ago)   6d23h
akash@sky:~$ kubectl delete po ak
pod "ak" deleted
akash@sky:~$ kubectl get pod
No resources found in default namespace.

akash@sky:~$ docker ps
CONTAINER ID   IMAGE                                 COMMAND                  CREATED      STATUS          PORTS                                                                                                                                  NAMES
f897b04f4708   gcr.io/k8s-minikube/kicbase:v0.0.37   "/usr/local/bin/entr…"   7 days ago   Up 13 minutes   127.0.0.1:49157->22/tcp, 127.0.0.1:49156->2376/tcp, 127.0.0.1:49155->5000/tcp, 127.0.0.1:49154->8443/tcp, 127.0.0.1:49153->32443/tcp   minikube
akash@sky:~$ kubectl get po --namespace kube-system
NAME                                      READY   STATUS    RESTARTS       AGE
calico-kube-controllers-7bdbfc669-m5jwl   1/1     Running   8 (15m ago)    33d
calico-node-wqqmj                         1/1     Running   8 (15m ago)    33d
coredns-787d4945fb-jgq2f                  1/1     Running   8 (15m ago)    33d
etcd-minikube                             1/1     Running   8 (15m ago)    33d
kube-apiserver-minikube                   1/1     Running   9 (15m ago)    33d
kube-controller-manager-minikube          1/1     Running   8 (15m ago)    33d
kube-proxy-bfd9s                          1/1     Running   8 (15m ago)    33d
kube-scheduler-minikube                   1/1     Running   9 (15m ago)    33d
storage-provisioner                       1/1     Running   16 (14m ago)   33d
akash@sky:~$ kubectl get po -A
NAMESPACE              NAME                                        READY   STATUS      RESTARTS       AGE
ingress-nginx          ingress-nginx-admission-create-24v5t        0/1     Completed   0              33d
ingress-nginx          ingress-nginx-admission-patch-f5pvc         0/1     Completed   0              33d
ingress-nginx          ingress-nginx-controller-6cc5ccb977-pbh74   1/1     Running     8 (17m ago)    33d
kube-system            calico-kube-controllers-7bdbfc669-m5jwl     1/1     Running     8 (17m ago)    33d
kube-system            calico-node-wqqmj                           1/1     Running     8 (17m ago)    33d
kube-system            coredns-787d4945fb-jgq2f                    1/1     Running     8 (17m ago)    33d
kube-system            etcd-minikube                               1/1     Running     8 (17m ago)    33d
kube-system            kube-apiserver-minikube                     1/1     Running     9 (17m ago)    33d
kube-system            kube-controller-manager-minikube            1/1     Running     8 (17m ago)    33d
kube-system            kube-proxy-bfd9s                            1/1     Running     8 (17m ago)    33d
kube-system            kube-scheduler-minikube                     1/1     Running     9 (17m ago)    33d
kube-system            storage-provisioner                         1/1     Running     16 (16m ago)   33d
kubernetes-dashboard   dashboard-metrics-scraper-5c6664855-tz9pc   1/1     Running     3 (17m ago)    15d
kubernetes-dashboard   kubernetes-dashboard-55c4cbbc7c-jbtvd       1/1     Running     3 (17m ago)    15d
akash@sky:~$ kubectl create namespace myspace
namespace/myspace created
akash@sky:~$ kubectl get ns
NAME                   STATUS   AGE
ak                     Active   23d
default                Active   33d
ingress-nginx          Active   33d
kube-node-lease        Active   33d
kube-public            Active   33d
kube-system            Active   33d
kubernetes-dashboard   Active   15d
myspace                Active   4s
akash@sky:~$ kubectl config get-contexts
CURRENT   NAME                                                CLUSTER                                             AUTHINFO                                            NAMESPACE

*         minikube                                            minikube                                            minikube                                            default

akash@sky:~$ kubectl config set-context --current --namespace myspace
Context "minikube" modified.
```

