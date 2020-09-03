# Creating Virtual Machines

## Overview
    In this lab, you will explore the Virtual Machine instance options and create several VMs with different characteristics.

## Objectives

> In this lab, you explore the available options for VMs and see the differences between locations.

  -In this lab, you learn how to perform the following tasks:

  -Create several standard VMs
  
  -Create advanced VMs
  
  # Task 1: Create a utility virtual machine
 
  
    gcloud beta compute  instances create instance-1 --zone=us-central1-c --machine-type=n1-standard-1
    --subnet=default --no-address

# Task 2: Create a Windows virtual machine

    gcloud beta compute instances create instance-2 --zone=europe-west2-a --machine-type=n1-standard-2
    --subnet=default --tags=http-server,https-server --image=windows-server-2016-dc-core-v20200813 
    --image-project=windows-cloud --boot-disk-size=100GB --boot-disk-type=pd-ssd
    
    gcloud compute  firewall-rules create default-allow-http --direction=INGRESS --priority=1000 
    --network=default --action=ALLOW --rules=tcp:80 --source-ranges=0.0.0.0/0 --target-tags=http-server
    
    gcloud compute  firewall-rules create default-allow-https --direction=INGRESS --priority=1000 
    --network=default --action=ALLOW --rules=tcp:443 --source-ranges=0.0.0.0/0 --target-tags=https-server
    
# Task 3: Create a custom virtual machine

    gcloud beta compute  instances create instance-3 --zone=us-west1-b --machine-type=custom-6-32768 --subnet=default


# Connect via SSH to your custom VM
For the custom VM you just created, click SSH.

To see information about unused and used memory and swap space on your custom VM, run the following command:

    free
To see details about the RAM installed on your VM, run the following command:

    sudo dmidecode -t 17
To verify the number of processors, run the following command:

    nproc
To see details about the CPUs installed on your VM, run the following command:

    lscpu
To exit the SSH terminal, run the following command:

    exit


    

