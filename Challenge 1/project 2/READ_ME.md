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

## Enter the following script as the value for Startup script:

apt-get update \
apt-get install apache2 php php-mysql -y \
service apache2 restart 

-Leave the remaining settings as their defaults, and click Create.

## Task 3: Create a Cloud Storage bucket using the gsutil command line

>All Cloud Storage bucket names must be globally unique. To ensure that your bucket name is unique, these instructions will guide you to give your bucket the same name as your Cloud Platform project ID, which is also globally unique.
>
>Cloud Storage buckets can be associated with either a region or a multi-region location: US, EU, or ASIA. In this activity, you associate your bucket with the multi-region closest to the region and zone that Qwiklabs or your instructor assigned you to.


-For convenience, enter your chosen location into an environment variable called LOCATION. Enter one of these commands:
**export LOCATION=US**

-In Cloud Shell, the DEVSHELL_PROJECT_ID environment variable contains your project ID. Enter this command to make a bucket named after your project ID:

**gsutil mb -l $LOCATION gs://$DEVSHELL_PROJECT_ID**

-Retrieve a banner image from a publicly accessible Cloud Storage location:

**gsutil cp gs://cloud-training/gcpfci/my-excellent-blog.png my-excellent-blog.png**

-Copy the banner image to your newly created Cloud Storage bucket:

**gsutil cp my-excellent-blog.png gs://$DEVSHELL_PROJECT_ID/my-excellent-blog.png**

-Modify the Access Control List of the object you just created so that it is readable by everyone:

**gsutil acl ch -u allUsers:R gs://$DEVSHELL_PROJECT_ID/my-excellent-blog.png**

## Task 4: Create the Cloud SQL instance

## Task 5: Configure an application in a Compute Engine instance to use Cloud SQL

