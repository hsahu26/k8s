
kubectl create namespace ingress-space
kubectl create configmap nginx-configuration --namespace ingress-space

kubectl create serviceaccount ingress-serviceaccount --namespace ingress-space

kubectl create -f ingress-cluster-role.yaml
kubectl create -f ingress-cluster-binding.yaml

kubectl create -f default-backend-dc-sg.yaml

kubectl create -f default-backend-svc-sg.yaml

kubectl create -f ingress-controller-answer-file.yaml

kubectl create -f ingress-service.yaml 
	or 
kubectl expose deployment -n ingress-space ingress-controller --type=NodePort --port=80 --name=ingress --dry-run -o yaml >ingress.yaml
## Creating LB ### Lb should forward all http traffic this 


## change namespace, path and service port according to enviroment, you can use this same as openshift route now 
kubectl create -f ingress-resource.yaml


