# Minikube GUI tool for Kubernetes clusters

- _minikube start_: To start minikube instance
- _minikube dashboard_: For running Minikube dashboardon local host in browser.

Kubernetes — Container *Orchestation*

The technical definition of orchestration is execution of a defined workflow: first do A, then B, then C. In contrast, Kubernetes comprises a set of independent, composable control processes that continuously drive the current state towards the provided desired state.

# Abstraction layers of Kubernetes 
- Pod : It's an Abstraction / layer on deployed Docket containers. 
- Node: a node is an Abstraction / layer on top of the pods. 
- Every Kubernetes cluster is made of one Control plane and one or more worker nodes. 

# Kubernetes cluster components 
- Kube API : A Front end for communication with the Kubernetes  clusters 
- etcd stores all the cluster info in a ke value pair ( probably in YAML?)
- Kube-Scheduler: it monitors for pods deployed, but not inside any nodes. And, assigns the pods to some node based on resource requirements of the pod. 
- kube-controller-manager
       - monitors all nodes in a cluster for its health, responds when a node goes down. 
       - Job controller:
       - end-points controller
       - service account and token controller 
- cloud-controller-manager: it manages cloud specific control logic. Like, enabling communication with Kubernetes cluster with cloud API, etc. 


# Node components 
- a Kubelet, a process which runs in every node within a cluster to ensure containers are running efficiently in a pod. 
- Kube-proxy a process which runs in every node within a cluster which forms some service rules for enabling communication with the pods from within or outside the cluster.  
- Container runtime: it's a runtime responsible for running containers inside a cluster. Like Containerd, CRI-O. 
- Addons : One key Afdon is DNS server, which keeps record of all the DNS addresses of all Kubernetes services. 







# Learn more about Kube API server (a component inside Control plane)
# Learn more about kube-controller-manage. 
