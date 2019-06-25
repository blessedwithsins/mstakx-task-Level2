# mstakx-task-Level2

1. HA Kubernetes Cluster created on GCP via using Kubeadm. #NotCompleted 

https://blog.inkubate.io/install-and-configure-a-multi-master-kubernetes-cluster-with-kubeadm/

For rest of the tasks, I'm using existing cluster created in Level1.

2. Setup Jenkins for deployment purpose.

https://linuxize.com/post/how-to-install-jenkins-on-ubuntu-18-04/

3. Create namespace "development".  

kubectl create ns development

4. Guest-book application deployed in "development" namespace. Snippets are uploaded as well. 

git clone https://github.com/kubernetes/examples.git
cd examples/guestbook
kubectl -n development apply -f redis-master-deployment.yaml -f redis-master-service.yaml 
kubectl -n development apply -f redis-slave-deployment.yaml -f redis-slave-service.yaml
kubectl -n development apply -f frontend-deployment.yaml -f frontend-service.yaml

5. Helm Already configured to install ingress-controller for Level1 task. Below are the steps for same:-

curl -o get_helm.sh https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get
chmod +x get_helm.sh
./get_helm.sh
kubectl create serviceaccount --namespace kube-system tiller
kubectl create clusterrolebinding tiller-cluster-rule --clusterrole=cluster-admin --serviceaccount=kube-system:tiller
helm init --service-account tiller

6. Help to deploy application in Kubernetes cluster via CI Server. #NotCompleted 

7. Create namespace "monitoring"

kubectl create ns monitoring

8. Prometheus setup was done by following below link:-

https://linuxacademy.com/blog/kubernetes/running-prometheus-on-kubernetes/

9. Grafana setup was done by following below link:-

https://docs.portworx.com/portworx-install-with-kubernetes/operate-and-maintain-on-kubernetes/monitoring/monitoring-px-prometheusandgrafana.1/#installing-grafana

10. I tried to implement ELK Stack but couldn't complete it as I were having issues while deploying Elastic Search and due to time-limit, I couldn't finish it of. Although, Kibana was deployed successfully. Attached is the screen-shot for same. #NotCompleted 

11. Blue-Green deployment was done via following below link:-

https://www.ianlewis.org/en/bluegreen-deployments-kubernetes

12. Creation of Wrapper script. #NotCompleted 




