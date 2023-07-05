1.	Deploy Minikube.  
2.	Install kubectl and check kubectl is working.  
3.	Check available nodes.  
4.	Display detailed information about nodes.  
5.	Describe kube config.  
6.	Create basic nginx deployment and deploy nginx in nginx namespace.  
7.	Install Helm 3.  
8.	Check status of deployment, check pods’ logs. Check information about services. Why services is needed?  
9.	Deploy Jenkins Helm chart/helmfile from helm public charts repo. Create port-forwarding and reach Jenkins UI via browser.  
10.	Stop minikube.  
11.	Destroy minikube.

# Implementation
1. Cluster created in GCP. Install the Google Cloud SDK by following the instructions on https://cloud.google.com/sdk/docs/install  
2. gcloud components install kubectl  
   kubectl version  
3. kubectl get nodes
4. kubectl describe node <node-name>  
5. cat ./kube/config  
6. kubectl apply -f nginx-deployment.yaml(file attached)  
7. curl https://get.helm.sh/helm-v3.6.3-linux-amd64.tar.gz --output helm-v3.6.3-linux-amd64.tar.gz   
   tar -zxvf helm-v3.6.3-linux-amd64.tar.gz  
   sudo mv linux-amd64/helm /usr/local/bin/  
8. kubectl get deploy  
   kubectl get pods  
   kubectl logs <pod_id>  
   kubectl get svc  
9. helm install jenkins jenkins/jenkins -f values.yaml  
   kubectl get svc jenkins  
