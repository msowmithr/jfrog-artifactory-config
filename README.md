# jfrog-artifactory-config


1. Create StorageClass:  
kubectl apply -f storageclass/sc.yaml

2. Create PVC:  
kubectl apply -f pvc.yaml

3. Create deployment and service:  
kubectl apply -f deployment.yaml  
kubectl apply -f service.yaml

4. Create Ingress Controller:  
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.0.3/deploy/static/provider/cloud/deploy.yaml

5. Create Ingress:  
kubectl apply -f ingress.yaml

6. Verify deployment and service:  
kubectl get po  
kubectl get svc -n ingress-nginx (Verify Ingress Controller)  
kubectl get ingress -n namespace (Verify host and IP)  


**Note:** 
Map the IP with domain in /etc/hosts (or DNS server)  
Add insecure-registries in /etc/docker/daemon.json and restart the server (sudo service docker restart) if you haven't register your domain in Cloud DNS
