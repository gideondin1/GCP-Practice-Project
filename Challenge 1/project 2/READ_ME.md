#
## Task 2: Confirm that needed APIs are enabled
>In the GCP Console, on the Navigation menu (Navigation menu), click 
APIs & Services.Scroll down in the list of enabled APIs, and confirm
 that both of these APIs are enabled:

**Kubernetes Engine API**
**Container Registry API**

If either API is missing, click Enable APIs and Services at the top. 
Search for the above APIs by name and enable each for your current 
project. (You noted the name of your GCP project above.)

## Task 3: Start a Kubernetes Engine cluster
>Start cloud Shell

For convenience, place the zone that Qwiklabs assigned you to into an environment variable called MY_ZONE. At the Cloud Shell prompt, type this partial command:

export MY_ZONE=
e.g; 
export MY_ZONE=us-central1-a

>Start a Kubernetes cluster managed by Kubernetes Engine. 
Name the cluster webfrontend and configure it to run 2 nodes:

**gcloud container clusters create webfrontend --zone $MY_ZONE --num-nodes 2**

check your installed version of Kubernetes using the kubectl version command:

**kubectl version**

## Task 4: Run and deploy a container
>From your Cloud Shell prompt, launch a single instance of the nginx container. (Nginx is a popular web server.)

**kubectl create deploy nginx --image=nginx:1.17.10**

View the pod running the nginx container:

**kubectl get pods**

Expose the nginx container to the Internet:

**kubectl expose deployment nginx --port 80 --type LoadBalancer**

View the new service:

**kubectl get services**

Scale up the number of pods running on your service:

**kubectl scale deployment nginx --replicas 3**

Confirm that Kubernetes has updated the number of pods:

**kubectl get pods**

Confirm that your external IP address has not changed:

**kubectl get services**
