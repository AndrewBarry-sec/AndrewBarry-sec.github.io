---
layout: single
title: "Server Setup Guide"
date: 2025-10-31
categories: [tutorials]
tags: [server, homelab, linux, beginner]
excerpt: "Learn how to set up your first homelab/server."
---

*Published: October 31, 2025 | Tags: server, linux, homelab*



# Server Beginner's Guide
## foundational knowledge required
Whether or not you wish to set up a server with zero background knowledge or plenty background knowledge; you will end up with much more knowledge than what you started with, despite your lack of desire to do so.

It is absolutely possible to set up a server/homelab from only following guidelines and not functioning off of your own pre-existing wisdom. However, living off of the assumption that everything will go smoothly can be foolish, in the instance of troubleshooting knowledge will be necessary if you lack the patience to make up for it.

If you follow this guide with some degree of pre-existing server knowledge and plan to learn a lot in the process, then you can feel free to use it as a reference and not follow it exactly, with perfect precision. 

What knowledge do you actually need? (if any of the following words mentioned mean nothing to you, then make sure that they do)  
**MUST**  
-must know the absolute basics of pc hardware (ram, cpu, storage)  
-must know how a VM (virtual machine) works  
-must know the basics of networking (dhcp, private/public/static ip, subnet masks)    
**SHOULD**  
-basics in regards to the CLI of your chosen host windows/linux (this is in the 'should' category and not 'must', because CLI is easy to learn if you are actively using it, which you will be)  


If you have no pre-existing server knowledge and do not intend to struggle in your first setup, then follow it with exact precision and without alteration. But understand that the hardware components I have used may be either overkill or underkill based on your budgets and needs. 


## IMPORTANT considerations to note before you continue
*skip on to the next part if you intend on following the guide with exact precision*

### hardware specifics
Decisions need to be made in regards to your hardware, upgrades can always be added later (more ram, storage etc). But you should consider what the workload on the server will be.   light workload will require (approximately) a 2-4 core CPU with 8gb RAM  
medium to high will need 4-6 with 16gb RAM  
heavy will need 6+ cores and 32GB of RAM  

the weight of the workload is dependant on the amount of virtual machines you wish to have and the type of work you wish to do   

Heavy CPU workloads:  
-machine learning  
-security testing  
-streaming service with files that need transcoding (ideally you should aim for direct play so no transcoding is necessary, I'll discuss this later)  

Heavy RAM workloads:  
-many vms  
-many users  

Heavy Network workload:  
-file transfer  
-streaming  
-vpn server  

The network workload is more dependant on your personal network and less dependant on your server in and of itself. 

### network specifics
If the server is intended to only be used locally (inside the local network) then the network specifics are not as important. If no external access is occurring then you do not need to change anything about your network.

If you intend on accessing your network externally then you need to consider how this will happen  
 


##### 1: VPN
**Software:** Tailscale, WireGuard, OpenVPN

**Requirements:**
- Port forwarding (unless you use tailscale)

**Choose if:** you want security

**consideration:** if services like chrome casting is important to you it will most likely not work with external access considering chromecast typically prevents screensharing/casting when a VPN is being used 

---

##### 2: Direct Port Forwarding
**Software:** none needed

**Requirements:**  
- Port forwarding

**Choose this if:** You want simplicity and understand the security risks

---

##### 3: Reverse Proxy + Domain
**Software:** Nginx Proxy Manager, Cloudflare Tunnel, Tailscale Funnel, ngrok

**How it works:** Access your server via custom domain name (subdomain.domain.com)

**Requirements:**
- **with Port Forwarding:** Nginx Proxy Manager, Caddy, Traefik  
- **NO port forwarding (tunnel):** Cloudflare Tunnel, Tailscale Funnel, ngrok

**Choose this if:** you want a more professional look for external users. Additionally it is also a good option if you want no open ports

---   


## what you will need
your chosen computer  
The computer selected for reference is the NUC 13 PRO
