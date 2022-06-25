By default, the Pod is only accessible by its internal IP address within the Kubernetes cluster. To make the hello-node Container accessible from outside the Kubernetes virtual network, you have to expose the Pod as a Kubernetes Service.

We can expose the Pod to the public internet using the `kubectl expose` command.
For example:

```
kubectl expose deployment hello-node --type=LoadBalancer --port=8080
```

here `--type=LoadBalancer` flag indicates that you want to expose your Service outside of the cluster.

# To view the Service

Use `kubectl get services` command
