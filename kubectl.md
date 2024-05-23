# kubectl

* [Kubectl](https://kubernetes.io/docs/tasks/tools/#kubectl)
    * kubectl command line client (CLI) is a binary used to access and manage any Kubernetes cluster.
    * It is installed through Minikube and accessed through the `minikube kubectl` command, or it can be installed separately and run as a standalone tool.

### kubectl Configuration File

* To access the Kubernetes cluster, the kubectl client needs the control plane node endpoint and appropriate credentials to be able to securely interact with the API Server running on the control plane node.
* While starting Minikube, the startup process creates, by default, a configuration file, config, inside the .kube directory (often referred to as the kubeconfig), which resides in the user's home directory.
* The configuration file has all the connection details required by kubectl. By default, the kubectl binary parses this file to find the control plane node's connection endpoint, along with the required credentials.
* Multiple kubeconfig files can be configured with a single kubectl client. To look at the connection details, we can either display the content of the ~/.kube/config file (on Linux) or run the following command

```shell
kubectl config view
```