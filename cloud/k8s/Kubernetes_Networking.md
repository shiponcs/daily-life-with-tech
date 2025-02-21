# k8s networking
### What problems k8s networking solve?
##### 1. cross-node pod-pod connectivity (east-west traffic)
see- 

![image](https://github.com/user-attachments/assets/e25fc469-eefc-4a01-85b8-806d684abaf6)
 
##### Details

Requirement of k8s for network implementation:
- All pods can communicate with all other pods without NAT
- All nodes running pods can communicate with all pods (and vice-versa) without NAT
- IP that a pod sees itself as is the same IP that other pods see it as
