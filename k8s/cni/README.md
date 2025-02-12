- https://tetrate.io/blog/kubernetes-networking/
- Introduction to CNI: https://www.youtube.com/watch?v=YjjrQiJOyME
  
  Learning:
  1. How CNI fits in
  ![Screenshot from 2025-02-12 15-32-34](https://github.com/user-attachments/assets/b0ce6b8a-6df9-4d43-beec-971158609e18)
  CNI is not tied to k8s. It is a generalized interface that can be used by any container runtime (containerd/k8s, mesos, CRI-O).
  In a nutshell this is how CNI operates, the container runtime makes a call (eg: `ADD`) to the CNI to add network interface to the container.
  2. What is the CNI project?
     1. Spec (CNI runtime implementation, reference plugin implementation, https://github.com/containernetworking/cni):
       It is vendor neutral, used by Mesos, Cloudfoundy, k8s, CRI-O, Podman
       
     2. Set of reference plugins (https://github.com/containernetworking/plugins)
  3. Configuration format:
  4. Execution Flow:
     
     1. Basic Commands: `ADD`, `DEL`, `CHECK`, and `VERSION`
     2. Plugins are executables
     3. The runtime (kubelet in case of k8s) executes the CNI plugins as seperate programs and
     4. feeds json data and some container specific data and the plugin program gives back the response in json format.
     
     
     
  

  
