Docker runs on a single host.  Whether u create container or multiple containers, it always is created on that single host.  

Containers are not able to auto-heal 

Containers are not able to autoscale 

Docker is a simple platform and doesnot provide enterprise support. In real enterprise application, it should consist load balancer, firewall, autoheal, autoscale, api gateways.. 

 

 

Problems with docker 

Single Host 

Auto scaling 

Auto healing 

Enterprise support  

 

Solution: Kubernetes 

 

By default, kubernetes is a cluster( group of nodes). Kubernetes is installed in on master node and we create multiple worker nodes. In docker, if one container is taking high resource of the host, other containers will get affected and still run in same docker host. Whereas in kubernetes, if one container or Pod is taking high resource and other Pods are getting affected, then k8s will create Pods in other nodes and balance the performance. 

 

Kubernetes has replica-controller or replicasets yaml file where we can define the no. of pods that we need to have. Also there is a feature HPA(Horizontal Pod Autoscaler) which creates new pods automatically when current pods / containers load exceeds our predefined threshold. 

 

When existing pods get crashed or damaged in any way, Kubernetes will create new one automatically to replace the damaged pod/containers even before the existing container is down. 

 

K8s supports Enterprise Level Container Orchestration Platform.  
