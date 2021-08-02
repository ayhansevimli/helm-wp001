# Helm Chart Installation for Wordpress

        C:\Utils\DevOps\Containerisation\helm

        git clone https://github.com/ayhansevimli/helm-wp001.git

        cd helm-wp001

* Add repository

        helm repo add bitnami https://charts.bitnami.com/bitnami

* Install chart

        helm install my-wordpress bitnami/wordpress --version 12.0.0

* Check Installation

        helm list 

        kubectl get deployment

        kubectl get pod

        kubectl get replicaset

        kubectl get service
        
        kubectl get pv
        
        minikube service list


* Get the WordPress URL by running these commands:

  NOTE: It may take a few minutes for the LoadBalancer IP to be available.
        Watch the status with: 
        
        kubectl get svc --namespace default -w my-wordpress
        
* Access Application

        minikube service list

        minikube service my-wordpress
        
----------------------------------------------------------------------------------------------------------------------

* Specify each parameter using the --set key=value[,key=value] argument to helm install. For example,

        helm install my-wordpress \
          --set wordpressUsername=admin \
          --set wordpressPassword=password \
          --set mariadb.auth.rootPassword=secretpassword \
            bitnami/wordpress

OR

        helm install my-wordpress --set wordpressUsername=admin --set wordpressPassword=password --set mariadb.auth.rootPassword=secretpassword bitnami/wordpress

----------------------------------------------------------------------------------------------------------------------

* To show you a list of all deployed releases.
        
        helm list 
        # or
        helm ls

* Uninstall chart & Cleanup

        helm uninstall my-wordpress
        
        kubectl delete pvc --all
        
        helm list
        
        kubectl get deployment

        kubectl get pod -o wide

        kubectl get replicaset

        kubectl get service

        kubectl get pv
        
        minikube service list
        
