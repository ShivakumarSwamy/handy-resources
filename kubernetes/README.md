# kubernetes

----
undefined [tip](#tip)
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
    * [delete resources](#delete-resources)
        + [delete a pod in current namespace](#delete-a-pod-in-current-namespace)
        + [delete a deployment in current namespace](#delete-a-deployment-in-current-namespace)
        + [delete a service in current namespace](#delete-a-service-in-current-namespace)
        + [delete a cronjobs in current namespace](#delete-a-cronjobs-in-current-namespace)
        + [delete a job in current namespace](#delete-a-job-in-current-namespace)
        + [delete a statefulset in current namespace](#delete-a-statefulset-in-current-namespace)
        + [delete a replicaset in current namespace](#delete-a-replicaset-in-current-namespace)
- [server](#server)
    + [get supported api resources](#get-supported-api-resources)
    + [get supported api versions](#get-supported-api-versions)
- [client and server](#client-and-server)
    + [get client and server version](#get-client-and-server-version)
- [resources](#resources)
----

----
# tip
- Prefer passing always the namespace in the command, which will act as a caution showing explicitly the namespace we are working   
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
kubectl get ingress
```

### delete resources

#### delete a pod in current namespace
```shell
kubectl delete pods <POD_NAME>

kubectl delete pod <POD_NAME>
```

#### delete a deployment in current namespace
```shell
kubectl delete deployments.apps <DEPLOYMENT_NAME>

kubectl delete deploy <DEPLOYMENT_NAME>
```

#### delete a service in current namespace
```shell
kubectl delete services <SERVICE_NAME>

kubectl delete service <SERVICE_NAME>
kubectl delete svc <SERVICE_NAME>
```

#### delete a cronjobs in current namespace
```shell
kubectl delete cronjobs.batch <CRON_JOB_NAME>

kubectl delete cronjobs <CRON_JOB_NAME>
```

#### delete a job in current namespace
```shell
kubectl delete jobs.batch <JOB_NAME>

kubectl delete jobs <JOB_NAME>
```

#### delete a statefulset in current namespace
```shell
kubectl delete statefulsets.apps <STATEFULSET_NAME>

kubectl delete sts <STATEFULSET_NAME>
```

#### delete a replicaset in current namespace
```shell
kubectl delete replicasets.apps <REPLICASET_NAME>

kubectl delete rs <REPLICASET_NAME>
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