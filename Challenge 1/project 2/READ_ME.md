# Google Cloud Fundamentals: Getting Started with Cloud Storage and Cloud SQL
In this lab,the following tasks were performed:

## Objectives
-Creation of a Cloud Storage bucket and place an image into it.

-Creation of a Cloud SQL instance and configure it.

-Connecting to the Cloud SQL instance from a web server.

-Use the image in the Cloud Storage bucket on a web page.

## Task 1: Sign in to the Google Cloud Platform (GCP) Console
## Task 2: Deploy a web server VM instance
-In the GCP Console, on the Navigation menu (Navigation menu), click Compute Engine > VM instances.

-Click Create.

-On the Create an Instance page, for Name, type bloghost

-For Region and Zone, select the region and zone assigned by Qwiklabs.

-For Machine type, accept the default.

-For Boot disk, if the Image shown is not Debian GNU/Linux 9 (stretch), click Change and select Debian GNU/Linux 9 (stretch).

-Leave the defaults for Identity and API access unmodified.

-For Firewall, click Allow HTTP traffic.

-Click Management, security, disks, networking, sole tenancy to open that section of the dialog.

Enter the following script as the value for Startup script:
apt-get update
apt-get install apache2 php php-mysql -y
service apache2 restart
##

## To create a VM instance using the gcloud command-line interface , execute this command:

gcloud compute instances create "my-vm-2" \
--machine-type "n1-standard-1" \
--image-project "debian-cloud" \
--image "debian-9-stretch-v20190213" \
--subnet "default"

//text in quotes are variables 
