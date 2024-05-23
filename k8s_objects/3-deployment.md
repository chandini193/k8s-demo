# Deployment

* Deployment objects provide declarative updates to Pods and ReplicaSets. 
* The DeploymentController is part of the control plane node's controller manager, and as a controller it also ensures that the current state always matches the desired state of our running containerized application. 
* It allows for seamless application updates and rollbacks, known as the default RollingUpdate strategy, through rollouts and rollbacks, and it directly manages its ReplicaSets for application scaling. 
* It also supports a disruptive, less popular update strategy, known as Recreate. 

To list all the deployment revisions
```shell
kubectl rollout history deployment <nginx-deployment>
```

To get the details of specific revision
```shell
kubectl rollout history deploy nginx-deployment --revision=2
```

To roll back to desired revision
```shell
kubectl rollout undo deployment nginx-deployment --to-revision=1
```
