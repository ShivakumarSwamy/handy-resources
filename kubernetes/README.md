# kubernetes

----
- [config](#config)
    * [context](#context)
        + [current context](#current-context)
        + [get all contexts](#get-all-contexts)
        + [use context](#use-context)
        + [get all info about current context only](#get-all-info-about-current-context-only)
- [k8s resources](#k8s-resources)
    * [get resources](#get-resources)
        + [get all pods in all namespaces](#get-all-pods-in-all-namespaces)
        + [get all pods in current namespace](#get-all-pods-in-current-namespace)
        + [get pods from specific namespace](#get-pods-from-specific-namespace)
        + [get cronjobs in current namespace](#get-cronjobs-in-current-namespace)
        + [get jobs in current namespace](#get-jobs-in-current-namespace)
        + [get deployments in current namespace](#get-deployments-in-current-namespace)
        + [get statefulset in current namespace](#get-statefulset-in-current-namespace)
        + [get replicasets in current namespace](#get-replicasets-in-current-namespace)
        + [get services in current namespace](#get-services-in-current-namespace)
        + [get ingress in current namespace](#get-ingress-in-current-namespace)
- [server](#server)
    + [get supported api resources](#get-supported-api-resources)
    + [get supported api versions](#get-supported-api-versions)
- [client and server](#client-and-server)
    + [get client and server version](#get-client-and-server-version)
- [resources](#resources)
----

## config

### context

#### current context

```shell
kubectl config current-context
```

#### get all contexts
```shell
kubectl config get-contexts
```

#### use context 
```shell
kubectl config use-context <YOUR_SUPER_CLUSTER_CONTEXT_NAME>
```

#### get all info about current context only
```shell
kubectl config view --minify 
```

## k8s resources

### get resources

#### get all pods in all namespaces
```shell
kubectl get pods --all-namespaces

kubectl get pods -A
```

#### get all pods in current namespace
```shell
kubectl get pods

kubectl get pod
```

#### get pods from specific namespace
```shell
kubectl --namespace <YOUR_NAMESPACE> get pods
```

#### get cronjobs in current namespace 
```shell
kubectl get cronjobs.batch

kubectl get cronjob
```

#### get jobs in current namespace
```shell
kubectl get jobs.batch

kubectl get job
```

#### get deployments in current namespace
```shell
kubectl get deployments.apps

kubectl get deploy
```

#### get statefulset in current namespace
```shell
kubectl get statefulsets.apps

kubectl get sts
```

#### get replicasets in current namespace
```shell
kubectl get replicasets.apps

kubectl get rs
```

#### get services in current namespace
```shell
kubectl get services

kubectl get service
kubectl get svc 
```

#### get ingress in current namespace
```shell
kubectl get services

kubectl get service
kubectl get svc 
```

## server

#### get supported api resources 
```shell
kubectl api-resources
```

#### get supported api versions
```shell
kubectl api-versions
```

## client and server

#### get client and server version
```shell
kubectl version
```

## resources

- [kubectl cheat sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [kubectx + kubens](https://github.com/ahmetb/kubectx)