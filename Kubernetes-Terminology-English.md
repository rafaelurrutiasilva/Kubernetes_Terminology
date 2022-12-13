|Terms |Definitions |
| :- | :- |
|[Admission controller](#0001) |Code that validates or mutates resources to enforce policy. Runs as part of the API admission chain immediately after authentication and authorization. |
|[Annotation](#0001)|Object metadata often used to expose alpha or beta capabilities, or integrate with 3rd-party systems. |
|[API](#0002)|Application Programming Interface. In the case of Kubernetes, all resources are defined in the API, which is RESTful and exposed via the API server. |
|[API group](#0003)|A set of related API resources. For example, networking resources are usually located in the networking.k8s.io API group. |
|[API resource](#0004)|All Kubernetes objects, such as Pods, Deployments and Services, are defined in the API as resources. |
|[API Server](#0005)|Exposes the API on a secure port over HTTPS. Runs on the control plane. |
|[Cloud controller manager](#0006)|Control plane service that integrates with underlying cloud platform. For example, when creating a LoadBalancer Service, the cloud controller manager implements the logic to provision one of the underlying cloud’s internet-facing load-balancers. |
|[Cloud native](#0007)|A loaded term and means different things to different people. Cloud native is a way of designing, building, and working with modern applications and infrastructure. I personally consider an application to be cloud native if it can self-heal, scale on-demand, perform rolling updates, and possibly rollbacks. |
|[ConfigMap](#0008)|Kubernetes object used to hold non-sensitive configuration data. A great way to add custom configuration data to a generic container, at runtime, without editing the image. |
|[Container](#0009)|Lightweight environment for running modern apps. Each container is a virtual operating system with its own process tree, filesystem, shared memory, and more. One container runs one application process. |
|[Container Network Interface (CNI)](#00010)|Pluggable interface enabling different network topologies and architectures. 3rd-parties provide CNI plugins that enable overlay networks, BGP networks, and various implementations of each. |
|[Container runtime](#00011)|Low-level software running on every cluster Node responsible for pulling container images, starting containers, stopping containers, and other low-level container operations. Typically: containerd, Docker, or cri-o. Docker was deprecated in Kubernetes 1.20 and support will be removed in a future version. |
|[Container Runtime Interface (CRI)](#00012)|Low-level Kubernetes feature that allows container runtimes to be pluggable. With the CRI you can choose the best container runtime for your requirements (Docker, containerd, cri-o, kata, etc.) |
|[Container Storage Interface (CSI)](#00013)|Interface enabling external 3rd-party storage systems to integrate with Kubernetes. Storage vendors write a CSI driver/plugin that runs as a set of Pods on a cluster and exposes the storage system’s enhanced features to the cluster and applications |
|[Controller](#00014)|Control plane process running as a reconciliation loop monitoring the cluster and making the necessary changes so the observed state of the cluster matches desired state. |
|[control plane](#00015)|The brains of every Kubernetes cluster. Comprises the API, API server, scheduler, all controllers, and more. These components run on all control plane nodes of every cluster. |
|[Control plane node](#00016)|A cluster node hosting control plane services. Usually doesn’t run user applications. You should deploy 3 or 5 for high availability. |
|[Cluster](#00017)|A set of worker and control plane nodes that work together to run user applications |
|[Cluster store](#00018)|Control plane feature that holds the state of the cluster and apps. Typically based on the etcd distributed data store and runs on the control plane. Can be deployed to its own cluster for higher performance and higher availability. |
|[containerd](#00019)|Container runtime. Default on many modern clusters. Donated to the CNCF by Docker, Inc. |
|[cri-o](#00020)|Container runtime. Commonly used in OpenShift based Kubernetes clusters. |
|[CRUD](#00021)|The four basics: Create, Read, Update, and Delete operations used by many storage systems.|
|[Custom Resource Definition (CRD)](#00022)|API resource used for adding your own resources to the Kubernetes API. |
|[Data plane](#00023)|The worker Nodes of a cluster that host user applications. |
|[Deployment](#00024)|Controller that deploys and manages a set of stateless Pods. Performs rollouts and rollbacks, and can self-heal. Uses a ReplicaSet controller to perform scaling and self-healing operations. |
|[Desired state](#00025)|What the cluster and apps should be like. For example, the desired state of an application microservice might be 5 replicas of xyz container listening on port 8080/tcp. Vital to reconciliation. |
|[Endpoints object](#00026)|Up-to-date list of healthy Pods matching a Service’s label selector. Basically, it’s the list of Pods a Service will send traffic to. Might eventually be replaced by EndpointSlices.|
|[etcd](#00027)|The open-source distributed database used as the cluster store on most Kubernetes clusters.|
|[Ingress](#00028)|API resource that exposes multiple internal Services over a single external-facing LoadBalancer Service. Operates at layer 7 and implements path-based and host-based HTTP routing.|
|[Ingress class](#00029)|API resource that allows you to specify multiple different Ingress controllers on your cluster. |
|[Init container](#00030)|A specialised container that runs and completes before the main app container starts. Commonly used to check/initialize the environment for the main app container. |
|[JSON](#00031)|JavaScript Object Notation. The preferred format for sending and storing data used by Kubernetes. |
|[K8s](#00032)|Shorthand way to write Kubernetes. The “8” replaces the eight characters between the “K” and the “s” of Kubernetes. Pronounced “Kates”. The reason why people say Kubernetes’ girlfriend is called Kate. |
|[Kubectl](#00033)|Kubernetes command line tool. Sends commands to the API server and queries state via the API server.|
|[Kubelet](#00034)|The main Kubernetes agent running on every cluster Node. It watches the API Server for new work assignments and maintains a reporting channel back. |
|[Kube-proxy](#00035)|Runs on every cluster node and implements low-level rules that handle routing of traffic from Services to Pods. You send traffic to stable Service names and kube-proxy makes sure the traffic reaches Pods. |
|[Label](#00036)|Metadata applied to objects for grouping. Works with label selectors to match Pods with higher level controllers. For example, Services send traffic to Pods based on sets of matching labels. |
|[Label selector](#00037)|Used to identify Pods to perform actions on. For example, when a Deployment performs a rolling update, it knows which Pods to update based on its label selector – only Pods with the labels matching the Deployment’s label selector will be replaced and updated. |
|[Manifest file](#00038)|YAML file that holds the configuration of one or more Kubernetes objects. For example, a Service manifest file is typically a YAML file that holds the configuration of a Service object. When you post a manifest file to the API Server, its configuration is deployed to the cluster.|
|[Microservices](#00039)|A design pattern for modern applications. Application features are broken into their own small applications (microservices/containers) and communicate via APIs. They work together to form a useful application. |
|[Namespace](#00040)|A way to partition a single Kubernetes cluster into multiple virtual clusters. Good for applying different quotas and access control policies on a single cluster. Not suitable for strong workload isolation. |
|[Node](#00041)|Also known as worker node. The nodes in a cluster that run user applications. Runs the kubelet process, a container runtime, and kube-proxy. |
|[Observed state](#00042)|Also known as current state or actual state. The most up-to-date view of the cluster and running applications. Controllers are always working to make observed state match desired state.|
|[Orchestrator](#00043)|A piece of software that deploys and manages apps. Modern apps are made from lots of small microservices that work together to form a useful application. Kubernetes orchestrates/manages these and keeps them healthy, scales them up and down, and more… Kubernetes is the de facto orchestrator of microservices apps based on containers. |
|[Persistent Volume (PV)](#00044)|Kubernetes object used to map storage volumes on a cluster. External storage resources must be mapped to PVs before they can be used by applications. |
|[Persistent Volume Claim (PVC)](#00045)|Like a ticket/voucher that allows an app to use a Persistent Volume (PV). Without a valid PVC, an app cannot use a PV. Combined with StorageClasses for dynamic volume creation. |
|[Pod](#00046)|Smallest unit of scheduling on Kubernetes. Every container running on Kubernetes must run inside a Pod. The Pod provides a shared execution environment – IP address, volumes, shared memory etc. |
|[RBAC](#00047)|Role-based access control. Authorization module the determines whether authenticated users can perform actions against cluster resources. |
|[Reconciliation loop](#00048)|A controller process watching the state of the cluster, via the API Server, ensuring observed state matches desired state. Moist controllers, such as the Deployment controller, run as a reconciliation loop. |
|[ReplicaSet](#00049)|Runs as a controller and performs self-healing and scaling. Used by Deployments. |
|[REST](#00050)|REpresentational State Trasfer. The most common architecture for creating web-based APIs. Uses the common HTTP methods (GET, POST, PUT, PATCH, DELETE) to manipulate and store objects. |
|[Secret](#00051)|Like a ConfigMap for sensitive configuration data. A way to store sensitive data outside of a container image, and have it inserted into a container at runtime. |
|[Service](#00052)|Capital “S”. Kubernetes object for providing network access to apps running in Pods. By placing a Service in front of a set of Pods, the Pods can fail, scale up and down, and be replaced without the network endpoint for accessing them changing. Can integrate with cloud platforms and provision internet-facing load-balancers. |
|[Service mesh](#00053)|Infrastructure software that enables features such as encryption of Pod-to-Pod traffic, enhanced network telemetry, and advanced routing. Common service meshes used with Kubernetes include Consul, Istio, Linkerd, and Open Service Mesh. Others also exist. |
|[Sidecar](#00054)|A special container that runs alongside, and augments, a main app container. Service meshes are often implemented as sidecar containers that are injected into Pods and add network functionality.|
|[StatefulSet](#00055)|Controller that deploys and manages stateful Pods. Similar to a Deployment, but for stateful applications. |
|[Storage Class (SC)](#00056)|Way to create different storage tiers/classes on a cluster. You may have an SC called “fast” that creates NVMe-based storage (Non-Volatile Memory Express), and another SC called “medium-three-site” that creates slower storage replicated across three sites. |
|[Volume](#00057)|Generic term for persistent storage. |
|[Worker node](#00058)|A cluster node for running user applications. Sometimes called a “Node” or “worker”. |
|[YAML](#00059)|Yet Another Markup Language. The configuration language you normally write Kubernetes configuration files in. It’s a superset of JSON|

