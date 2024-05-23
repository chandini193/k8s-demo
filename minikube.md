# Minikube

* [Minikube](https://minikube.sigs.k8s.io/docs/start/)
    * It is one of the easiest, most flexible and popular methods to run an all-in-one or a multi-node local Kubernetes cluster, isolated by Virtual Machines (VM) or Containers, run directly on our workstations.
    * Minikube is the tool responsible for the installation of Kubernetes components, cluster bootstrapping, and cluster tear-down when no longer needed.
    * **Note:** Docker/ Docker desktop should be running

1. Start Minikube. We can start Minikube with the minikube start command, which bootstraps a single-node cluster with the latest supported stable Kubernetes version release.
    ```shell
    minikube start
    ```
2. Check the status. With the minikube status command, we display the status of the Minikube cluster.
    ```shell
    minikube status
    ```
3. Stop Minikube. With the minikube stop command, we can stop Minikube. This command stops all applications running in Minikube, safely stops the cluster and the Docker container, preserving our work until we decide to start the Minikube cluster once again, while preserving the Minikube Docker container
    ```shell
    minikube stop
    ```
4. Remove Minikube. The minikube delete command completely removes Minikube and the Minikube Docker container. This command should be attempted only when the Minikube cluster is to be decommissioned. All work will be lost after the completion of this command.
    ```shell
    minikube delete
    ```
5. Access K8s dashboard, Web-based User Interface (Web UI) to interact with a Kubernetes cluster to manage resources and containerized applications. Minikube installs the Dashboard as an addon, but it is disabled by default.
    * To list the addons
   ```shell
   minikube addons list
   ```
    * To enable addons metrics-server and dashboard
   ```shell
   minikube addons enable metrics-server
   ```
   ```shell
   minikube addons enable dashboard
   ```
    * To access K8s dashboard
   ```shell
   minikube dashboard
   ```