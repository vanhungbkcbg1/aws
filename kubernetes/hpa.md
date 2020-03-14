###to install hpa on aws service
Horizontal Pod Autoscaler (HPA) scales pod trong deployment or replicaset
no la module san co trong kubernetes
The controller manager queries the resource utilization against 
the metrics specified in each HorizontalPodAutoscaler definition. 
It obtains the metrics from either the resource metrics API (for per-pod resource metrics), or the custom metrics API (for all other metrics)
* ####cai dat metric server
   ####
   #####cai dat hem
   
   ```curl -sSL https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash```
   
   ```helm repo add stable https://kubernetes-charts.storage.googleapis.com/```
   
   ```helm search repo stable```
   
   ```helm completion bash >> ~/.bash_completion
      . /etc/profile.d/bash_completion.sh
      . ~/.bash_completion
      source <(helm completion bash)```
### metric server
```helm completion bash >> ~/.bash_completion
   . /etc/profile.d/bash_completion.sh
   . ~/.bash_completion
   source <(helm completion bash)
```
###confirm metric available
```kubectl get apiservice v1beta1.metrics.k8s.io -o yaml```
### the result shoud be

```status:
  conditions:
  - lastTransitionTime: "2020-02-18T21:33:26Z"
    message: all checks passed
    reason: Passed
    status: "True"
    type: Available`````


https://eksworkshop.com/beginner/080_scaling/test_hpa/