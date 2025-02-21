Talks:
- [Liberating Kubernetes From Kube-proxy and Iptables - Martynas Pumputis, Cilium](https://www.youtube.com/watch?v=bIRwSIwNHC0): 
Very good one to get a good grasp over the overall implementation details of _Cilium using eBPF_ and performance discrepancy between Cilium and
iptables and ipvs based CNI.


  Learning:
  
  ![image](https://github.com/user-attachments/assets/309ee23f-f804-4291-9596-eea037a1b300)
  ![Screenshot from 2025-02-06 19-22-36](https://github.com/user-attachments/assets/214e1521-33ec-47fb-a2f5-4ef81aac7cf7)*Overhead of using iptables (i.e. Netfilter)

  How kube-proxy takes advantages of Netfilter chains:
  ![Screenshot from 2025-02-06 19-28-24](https://github.com/user-attachments/assets/2aa2a84e-94f6-4244-b307-c596f381c932)

  How can we get rid of this long list of chains? Yes, eBPF.
  ![Screenshot from 2025-02-06 19-30-34](https://github.com/user-attachments/assets/9d4cbe6f-9bad-44d2-bdbb-103584080fad)
  ![image](https://github.com/user-attachments/assets/95e15830-24d7-43cc-a2d9-d80996cf53f8)
  ![Screenshot from 2025-02-06 19-35-28](https://github.com/user-attachments/assets/4b17da3a-83ef-4bc9-8f78-561807ed5da9)

  
  
  


  

  

  


  
