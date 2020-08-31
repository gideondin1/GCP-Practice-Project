# VPC Networking
## Overview
>Google Cloud Virtual Private Cloud (VPC) provides networking functionality to Compute Engine virtual machine (VM) instances, Kubernetes Engine containers, and the App Engine flexible environment. In other words, without a VPC network, you cannot create VM instances, containers, or App Engine applications. Therefore, each Google Cloud project has a default network to get you started.

>You can think of a VPC network as similar to a physical network, except that it is virtualized within Google Cloud. A VPC network is a global resource that consists of a list of regional virtual subnetworks (subnets) in data centers, all connected by a global wide area network (WAN). VPC networks are logically isolated from each other in Google Cloud.

>In this lab, you create an auto mode VPC network with firewall rules and two VM instances. Then, you convert the auto mode network to a custom mode network and create other custom mode networks as shown in the network diagram below. You also test connectivity across networks.

## Objectives
>In this lab, you learn how to perform the following tasks:

-Explore the default VPC network
-Create an auto mode network with firewall rules
-Convert an auto mode network to a custom mode network
-Create custom mode VPC networks with firewall rules
-Create VM instances using Compute Engine
-Explore the connectivity for VM instances across VPC networks