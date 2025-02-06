Problem: Let's say you have created a k3s cluster and now you want to access it from outside the network. To do that you need
to assign a public IP to your machine the cluster is running on. Recently I installed tailscale on the VM (on which a k3s cluster
was running) so that I can access the cluster from my home. Here's how I did that.

1. First we need to add the Tailscale IP to `tls-san` of the cluster. 
> By default, configuration files are read from /etc/rancher/k3s/config.yaml and /etc/rancher/k3s/config.yaml.d/*.yaml in alphabetical order. [1](https://docs.k3s.io/installation/configuration#multiple-config-files)

So, we create a config file if it doesn't exist:
```bash
cd /etc/rancher/k3s
touch config.yaml
```
And, add this content to the file:
```bash
tls-san:
  - <tailscale-ip>
  - <other ips>
```
2. Restart k3s cluster service
 ```bash
 systemctl restart k3s
 ```
3. Collect the update kubeconfig file and update the following field:
```bash
    server: <tailscale-ip>:6443
 ```
