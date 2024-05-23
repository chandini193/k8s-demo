### **Namespace**
In Kubernetes, a namespace is a virtual cluster that provides a way to divide and isolate resources within a cluster. It allows you to create multiple virtual clusters within a single physical cluster, providing a logical separation of resources.

Here are the key points to understand about Namespaces:

### **Isolation and Resource Segregation:**
Namespaces provide a way to isolate and segregate resources within a Kubernetes cluster. By default, all resources are created in the default namespace. However, you can create additional namespaces to organize and separate resources based on teams, projects, environments, or any other logical grouping.

### **Scoping and Visibility:**
Each Namespace has its own scope, meaning that resources within a Namespace are only visible and accessible within that Namespace. This allows different teams or projects to work independently without interfering with each other's resources.

### **Resource Namespacing:**
Most Kubernetes resources, such as Pods, Services, Deployments, ConfigMaps, and Secrets, can be created within a specific Namespace. This ensures that resources are namespaced and unique within that Namespace, preventing naming conflicts across different Namespaces.

### **Access Control and RBAC:**
Namespaces provide a boundary for access control and Role-Based Access Control (RBAC) policies. You can define RBAC rules to grant or restrict access to specific Namespaces, allowing fine-grained control over who can access and manage resources within each Namespace.

### **Resource Quotas and Limits:**
Namespaces allow you to set resource quotas and limits to control the allocation of compute resources (CPU, memory, storage) within a Namespace. This helps prevent resource abuse and ensures fair resource distribution among different teams or projects.

### **Monitoring and Management:**
Namespaces provide a way to organize and manage resources within a cluster. You can monitor and manage resources at the Namespace level, making it easier to track resource utilization, troubleshoot issues, and apply policies specific to each Namespace.

### **Default Namespace:**
The default Namespace is created automatically in a Kubernetes cluster. It is the default Namespace where resources are created if no Namespace is specified. However, it is recommended to create additional Namespaces to organize and manage resources effectively.

Namespaces are a powerful feature in Kubernetes that enable multi-tenancy, resource isolation, and access control within a cluster. They provide a way to logically separate and manage resources, making it easier to scale and maintain complex applications and environments.

### **Namespace in action**

#### List the namespace on the cluster

```shell
kubectl get namespaces | ns
```

#### Creating a new namespace

```shell
kubectl create namepsace test
```

#### Listing resources in test namespace

``` shell
kubectl get pods --namesapce test
```

```shell
kubectl get pods -n=test 
```

#### creating resources in new namespace

```shell
kubectl run nginx --image=nginx --port 8080 -n test
```

#### Updating current context in k8s configuration

```shell
kubectl config set-context --current --namespace=test
```