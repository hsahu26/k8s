
### Pre-Requesiste for autoscalar ###
mertic pod should use hostNetwork as API servre need to comunicate with metric pod (already change in metric deployment)
## following need to change to use new metric servet and keep away from heapster
Go in to  /etc/kubernetes/manifests/kube-controller-manager.yaml and make below parameter true 
--horizontal-pod-autoscaler-use-rest-clients=true

