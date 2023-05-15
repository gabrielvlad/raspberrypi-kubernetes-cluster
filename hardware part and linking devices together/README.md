# Hardware documentation part raspberrypi-kubernetes-cluster repository

Setting Up hardware infrastructure for a Raspberry Pi Kubernetes Cluster

The Raspberry Pi Kubernetes Cluster is a cost-effective and efficient way to set up a Kubernetes cluster. There are two main ways to set up the cluster for the hardware part:

1. Boot from storage device in this case example SD cards with a switch acting as the IP assigner and internet provider.
2. Main node device provides boot over the network and has a storage HDD (or better) as the image boot loader. The main node device also acts as a DHCP server, so it assigns IPs for the worker nodes and provides internet.

I explain each method more in-depth below:

## Method 1: Boot from SD cards with a switch acting as the IP assigner and internet provider

For this method, each node in your cluster will boot from an SD card that contains the necessary operating system and software. The switch that connects your nodes will assign IP addresses (likely through DHCP) and provide a connection to the internet.

_Diagram Placeholder_

_Underneath Diagram Text_:

**Pros**: This method is simpler to set up, as each node is self-contained and doesn't rely on another node to boot. It's also more resilient, as a failure in one node won't prevent other nodes from booting.

**Cons**: Managing the software on each node can be more complicated, because you'll need to update each SD card individually. It may also be less efficient in terms of storage, because each node needs its own copy of the boot image.

Summary:

This method is easier to get into but provides less control over your setup, the advatage being the ease of setup

## Method 2: Main node provides boot over the network and has a storage HDD as the image boot loader, also acting as DHCP server

For this method, one node (the "main" node) is responsible for providing the boot image to the other nodes over the network created by linking them together. It also assigns IP addresses and provides an internet connection.

_Diagram Placeholder_

_Underneath Diagram Text_:

**Pros**: This method is more efficient in terms of storage, because you only need one copy of the boot image. It's also easier to manage the software, because you only need to update the boot image in one place.

**Cons**: Setting up this method can be more complex and potentially less resilient, because a failure in the main node could prevent other nodes from booting. It also puts more load on the main node, which needs to serve the boot image and handle DHCP requests in addition to running its own workloads.

Summary:
Requires more time invested in the initial setup but it offers more control over the setup and teaches you more about how everything connects (for me I consider this quite valuable)

## Conclusion for the Two Methods

Regardless of the hardware setup method, once the nodes are up and running, you can install and configure Kubernetes in the same way. Kubernetes doesn't care how the nodes boot or get their IP addresses, as long as they can communicate with each other over the network.

References:

How to build a cluster official [raspberrypi.com](http://raspberrypi.com) documentation:

- [https://www.raspberrypi.com/tutorials/cluster-raspberry-pi-tutorial/](https://www.raspberrypi.com/tutorials/cluster-raspberry-pi-tutorial/)
