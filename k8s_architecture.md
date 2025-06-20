![image](https://github.com/user-attachments/assets/b21276ac-542f-4729-a4bb-9557875fff5b)

Since k8s is an enterprise level support, we create a **Master Node** and a **Worker Node**. 

 

In **Worker Node**: 

- **Pods** are deployed which is a wrapper around the container with advanced options. 

  

- **Container Runtime:**
  In k8s also, to run a container inside the pod, it requires container runtime. But unlike Docker, there are multiple options to "dockershim" such as 'containerd', 'crio', 'dockershim' 

 

- **Kubelet** is responsible for making sure the pod is running. Kubelet will inform a control node component if pod fails to run and manage to keep the pod in running state. That is Autohealing. 

 

- **Kubeproxy** is for networking in pod. It helps allocating IP address to every pods and also provides load balancing capability between pods which is needed for Autoscaling and balancing the traffic between multiple replica of pods. 

 

In **Control Node**: 

- **API server:** Core component of the k8s that basically exposes the k8s to external world.
  - Takes all the request from the external world.
  - If a user requests to create a Pod, then the API server decides that Node1 among multiple nodes is free and the pod can be created in Node1. 

- Scheduler: 
  - Scheduler will schedule the component/resource in the node decided by the API server. 
  - API server decides where to act 
  - Scheduler acts in the node decided by the API server. 

 - **'etcd':**
   - Is a key-value store
   - It stores entire kubernetes cluster information as key-value pair.
   - Acts as backup service that helps restoring the cluster 

- **Controller Manager:** 
  - K8s has multiple controllers.
  - For example, "Replicaset" controller will ensure the No. Of pods running as per we have specified in yaml file.
  - Now, Controller Manager job is to ensure all these controllers are running properly. 

- **Cloud Controller Manager(CCM):**
  - Today, multiple cloud services are in use.
  - K8s can be run on EKS(AWS), AKS(Azure), GKE(GC) cloud platform.
  - Suppose user creates a request for load balancer. Then K8s has to understand which cloud provider is it where load balancer is to be configured.
  - K8s has to translate the user request on to the API request that the mentioned cloud provider understands.
  - CCM handles the job 
