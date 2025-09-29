
Build a Kubernetes Cluster on AWS Cloud (EKS)
-- 
Deploy and manage applications on a cloud-managed Kubernetes cluster using AWS EKS and understand Kubernetes basics: deployments, services, scaling, and pod management.

Tools Used:
--
- AWS EKS– Managed Kubernetes cluster  
- kubectl– Kubernetes CLI  
- Docker– Container runtime for images  
- eksctl– EKS cluster and nodegroup management

 Output:
--
 deployment.yml (pod ):
 command:
 --
 # kubectl apply -f deployment.yml 
 # kubectl get pods
 NAME                              READY   STATUS             RESTARTS   AGE
nginx-deployment-96b9d695-54lhg   1/1     Running            0          14s
nginx-deployment-96b9d695-6mcld   1/1     Running            0          14s

-- service.yml :
command:
--
# kubectl apply -f service.yaml 
# kubectl get service
 NAME            TYPE           CLUSTER-IP       EXTERNAL-IP                                                              PORT(S)        AGE
kubernetes      ClusterIP      10.100.0.1       <none>                                                                     443/TCP        42m
nginx-service   LoadBalancer   10.100.201.138   a16851b5a42dd4ca680aa050e5417096-1478466367.ap-south-1.elb.amazonaws.com   80:31831/TCP   18s

--Scaling 
# kubectl scale deployment nginx-deployment --replicas=6
deployment.apps/nginx-deployment scaled
 kubectl get pods
NAME                              READY   STATUS             RESTARTS   AGE
nginx-deployment-96b9d695-54lhg   1/1     Running            0          25m
nginx-deployment-96b9d695-6mcld   1/1     Running            0          25m
nginx-deployment-96b9d695-lwkhm   1/1     Running            0          22s
nginx-deployment-96b9d695-mg495   1/1     Running            0          22s
nginx-deployment-96b9d695-qtwkc   1/1     Running            0          22s
nginx-deployment-96b9d695-zj796   1/1     Running            0          22s

 Commands for information about pods:
 --
# kubectl describe pod nginx-deployment-96b9d695-6mcld
# kubectl logs nginx-deployment-96b9d695-6mcld


