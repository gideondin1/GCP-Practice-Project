# Google Cloud Fundamentals: Getting Started with Compute Engine
In this lab,the following tasks were performed:

## Objectives
-Creation of Compute Engine virtual machine using the Google Cloud Platform (GCP) Console.

-Creation of Compute Engine virtual machine using the gcloud command-line interface.

-Test Connection between the two instances.

## To create a VM instance using the gcloud command-line interface , execute this command:

gcloud compute instances create "my-vm-2" \
--machine-type "n1-standard-1" \
--image-project "debian-cloud" \
--image "debian-9-stretch-v20190213" \
--subnet "default"

//text in quotes are variables 
