# Software documentation part and how the programs communicate with each other

What will be installed as the software part:

1. k3s as it is the Kubernetes distribution -must be
2. Rancher for oversight and overview of the k3s distribution -optional
3. Ansible for python automation (requires python 3 installed on the machine to work) -optional
4. Træfik for HTTP reverse proxy and load balancer -optional
5. Terraform for the hardware cluster resource usage in relation to the Kubernetes distribution
6. Terraform Cloud for overview and oversight of Terraform software installed

A-bit more detail in-depth below:

1.k3s - lightweight Kubernetes distribution developed by Rancher Labs it was designed to be easy to install and run on IoT devices as well as traditional servers.

Summary: It's a fully compliant Kubernetes distribution with some parts removed to reduce its footprint.

For managing the installed k3s distribution, is nice but not necessary to have Rancher.

2.**Rancher**

Rancher is an open-source platform for managing Kubernetes at scale. It provides the tools necessary to operate Kubernetes clusters, whether they're in the cloud or on-premises.

Summary:

Ansible is a tool for automating IT tasks (including but not limited to managing Kubernetes), while Rancher is a platform for managing Kubernetes specifically. They can be used together - for example, you could use Ansible to automate the setup and initial configuration of your Kubernetes nodes and then use Rancher to manage the resulting Kubernetes clusters.

For scripts automation and having your cluster do things for you.

3.**Ansible**

Ansible is an open-source software tool developed by Red Hat. Its primary function is to automate tasks such as configuration management, software deployment, and orchestration.

Summary

**Ansible** is primarily a configuration management tool. It excels at installing and managing software on existing servers. For example, after you've created a server, you could use Ansible to install web server software, copy over your website's code, start the web server, and so on.

for HTTP reverse proxy and load balancer

4.Træfik

Traefik is a modern HTTP reverse proxy and load balancer that makes deploying microservices easy. Traefik integrates with existing infrastructure components (Docker, Kubernetes, Consul, Etcd, Rancher, Amazon ECS, ...) and configures itself automatically and dynamically. Pointing Traefik at orchestrator is the only configuration step needed.

References:

How to install k3s and have Rancher for oversight::

- [https://www.youtube.com/watch?v=X9fSMGkjtug&t=1599s](https://www.youtube.com/watch?v=X9fSMGkjtug&t=1599s)

How to install the **Ansible and what it does:**

- [https://youtu.be/CbkEWcUZ7zM](https://youtu.be/CbkEWcUZ7zM)
