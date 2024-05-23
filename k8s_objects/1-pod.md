# Pods
A Pod is the smallest and most basic unit of deployment in Kubernetes. It represents a single instance of a running process within the cluster. A Pod encapsulates one or more containers, storage resources, and network settings that are tightly coupled and share the same lifecycle.

There are 2 ways to create any resource in kubernetes world.

1. Imperative: Use a CLI command to create any k8s resource.
   Creating a sample nginx pod
    ```shell
    kubectl run nginx --image=nginx --port 8080
    ```
2. Declarative: Describe a desired deployment state in a YAML (or JSON) file and apply the resource.

**Understand the K8s manifest files**

`apiVersion`: specifies the Kubernetes API version being used.

`kind`: indicates the object type that this YAML describes.

`metadata`: contains metadata about the object, including its name and labels. 
* `name`: name of the K8s object
* `labels` : are key-value pairs used to identify and organize resources, selects a subset of objects, based on the requirements in place

`spec`: defines the specifications of the pod.

**Example**

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  labels:
    run: nginx-pod
spec:
  containers:
  - name: nginx
    image: nginx:stable
    ports:
      - containerPort: 80
```

### Create the pod
```shell
kubectl apply -f ./1-pod.yaml
```

### Connecting to the pod
* To connect to a pod in Kubernetes, you can use the kubectl exec command. This command allows you to execute a command inside a running container within the pod. 
   Here's the basic syntax: This command opens an interactive shell session (-it) inside the specified pod, using the /bin/sh command.
   ```shell
   kubectl exec -it nginx-pod -- /bin/sh 
   ```
* If the pod has multiple containers, you can specify the container name using the -c or --container flag. For example: replace with the actual name of the container you want to connect to.
   ```shell
   kubectl exec -it <pod-name> -c <container-name> -- /bin/sh
   ```

### Access the pod
```shell
kubectl port-forward pod/nginx-pod 8080:80
```
   


