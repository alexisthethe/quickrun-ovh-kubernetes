Create a cluster with this [OVH tutorial](https://docs.ovh.com/asia/en/kubernetes/deploying-hello-world/#add-a-node-pool)

The following instructions come from this [OVH deploying tutorial](https://docs.ovh.com/asia/en/kubernetes/deploying-an-application/)

Download your cluster kubectl condifuration and place it here

Load kubectl configuration 

```
export KUBECONFIG=$(pwd)/kubeconfig.yml
```

Test the kubectl command configuration

```
kubectl cluster-info
```

Deploy
```
kubectl apply -f hello.yml -n default
```

Check available
```
kubectl get services -n default -l app=hello-world
```
When the `EXTERNAL-IP` is OK go visit the IP to see your website.

Clean up
```
kubectl delete service hello-world -n default
kubectl delete deploy hello-world-deployment -n default
```
