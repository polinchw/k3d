# k3d

## Description

Install a k3s Kubernetes cluster with k3d.

### Create cluster

```angular2html
k3d cluster create --config k3d.yaml
```

### Apply the Storage class

```angular2html
kub apply -f storageclass.yaml
```

### Start/Stop the cluster

Once the cluster is created it will run and we restarted when your PC is restarted.

#### Start

```angular2html
k3d cluster start mycluster
```

#### Stop

```angular2html
k3d cluster stop mycluster
```