# Infrastructure Preview
## Objectives
-In this lab, you learn how to perform the following tasks:

-Use Marketplace to build a Jenkins Continuous Integration environment.

-Verify that you can manage the service from the Jenkins UI.

-Administer the service from the Virtual Machine host through SSH.

# Task 1: Use Marketplace to build a deployment
-In the Cloud Console, on the Navigation menu , click Marketplace.
-Locate the Jenkins deployment by searching for Jenkins Certified by Bitnami.

# Task 2: Examine the deployment
# Task 3: Administer the service

Shut down and restart the services
-In the SSH window, enter the following command to shut down all the running services:

**sudo /opt/bitnami/ctlscript.sh stop**

-In the SSH window, enter the following command to restart the services:

**sudo /opt/bitnami/ctlscript.sh restart**
