# k3d

## Description

Install a k3s Kubernetes cluster with k3d.

### Create cluster

```angular2html
k3d cluster create mycluster --config k3d.yaml
```

### Apply the Storage class

```angular2html
kub apply -f storageclass.yaml
```

### Label the nodes

```angular2html
 kub label node k3d-mycluster-agent-1 nodetype=standard
 kub label node k3d-mycluster-agent-0 nodetype=pod
```

### Start/Stop the cluster

Once the cluster is created it will run and will restart when your PC is restarted.

#### Start

```angular2html
k3d cluster start mycluster
```

#### Stop

```angular2html
k3d cluster stop mycluster
```

#### Disable Traefik

```
k3d cluster create --config k3d.yaml --k3s-arg "--disable=traefik@server:0" 
```

##### Replace Traefik with Nginx

```
helm upgrade --install ingress-nginx ingress-nginx --repo https://kubernetes.github.io/ingress-nginx   --namespace ingress-nginx --create-namespace -f nginx-values.yaml  --version=v3.29.0
```

### Kubernetes Cluster Help

#### To add DNS records to a cluster's coredns follow the instructions here:

[https://coredns.io/2017/05/08/custom-dns-entries-for-kubernetes/](https://coredns.io/2017/05/08/custom-dns-entries-for-kubernetes/)

