# Logs & Troubleshooting

The kubectl logs command is used to retrieve the logs of a specific pod in Kubernetes. When running the kubectl logs command, you need to provide the name of the pod you want to retrieve the logs from. Here's the basic syntax:
```shell
kubectl logs <my-pod>
```
By default, the kubectl logs command retrieves the logs from the main container within the pod. If there are multiple containers within the pod, you can specify the container name using the -c or --container flag. For example:
```shell
kubectl logs <my-pod> -c <my-container>
```
This command retrieves the logs from the container named my-container within the my-pod pod.

Additionally, you can use other flags with the kubectl logs command to customize the output, such as -f to stream the logs in real-time or --tail to specify the number of lines to retrieve.
```shell
kubectl logs <my-pod> -c <my-container> -f
```