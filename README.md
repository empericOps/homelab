# ericlab
Documentation of my homelab + repository.

# Documentation

I don't expect this to be the neatest thing. I'm learning this as I go with some resources so I thought it would be beneficial to provide 
them as I go.
Essentially, my goal is to create a homelab using K8S nodes to learn how kubernetes works and the process of creating yaml for IaC and improving my skills as both a SysEngineer/SysAdmin.

I want to be able to host my own things internally (like most internet geeks) and be able to toy with some side projects without worrying too much about: "Do I have the VM space to do this?" I also feel like I can't toy as much as I used to be able to in my day-job, unfortunately, I can't push everything to prod.


# Video Resources Used:
	
So far: I've used a few videos on Youtube to help set up my K8S controller and nodes. I have no idea what I'm doing but shoutout to 
Learn Linux TV and his guide regarding using K8S on proxmox.
	
* https://www.youtube.com/watch?v=U1VzcjCB_sY
* https://www.learnlinux.tv/how-to-build-an-awesome-kubernetes-cluster-using-proxmox-virtual-environment/

Also checking out Mischa van den burg on Youtube; following a lot of his steps and learning them as I go on what is worthwhile. * 

* https://www.youtube.com/playlist?list=PL_JVnPgp2IReqn18A46SGh8yy5WVVWHAu

# Goals

### GitOps 

 With one of my goals being to learn IaC (Infrastructure as Code) - I decided on Flux as my choice. I got interested in GitOps and being able to push/pull as needed and version 
 control. I know I'm going to mess up. Part of the process right? Well, if I mess up, how can I revert and learn from my mistakes? I wouldn't be able to do it without some sort of Version 
 Control. That's where Flux comes in. Flux allows me to use "GitOps" so I can do some proper verison controlling.

 Check it out here: https://fluxcd.io/flux/installation/ 



### Applications

 * Grafana/Prometheus
		
 OK SO- 
 I ran into some snags with this one. I was able to get the K8 cluster to install Prometheus/Grafana using their documentation. I had to install Helm then I was able to get the repo to push down grafana. It's up. The problem that I'm having now is setting up the ingress NGINX to allow access through my network since I'm not hosting it on my local device but through some Proxmox VMs. To look into later this week. -Eric 3/20
 https://github.com/prometheus-community/helm-charts/blob/main/charts/kube-prometheus-stack/README.md
			
			Read through more of the documentation (and my favorite consultant, GPT), turns out I had to edit the svc itself 
				kubectl get svc -n namespace
				kubectl edit svc servicename -n namespace
				change the line "type: ClusterIP" to "type: NodePort"
				EDIT: before I forget, make sure you have the NGINX ingress installed or else it won't work!!!! View kubernetes documentation on this: https://github.com/kubernetes/ingress-nginx/blob/main/docs/deploy/index.md#quick-start

 * Plex 
 * Adguard for DNS 
 * Myfin (budgetting application) 
 * Homepage (intranet, type of deal.)
 * Home Assistant?


