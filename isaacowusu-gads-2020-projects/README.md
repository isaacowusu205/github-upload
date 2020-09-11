# IsaacOwusu GADS Project Submissions

## Google Cloud Fundementals: Getting Started with Compute Engine

Objectives in the lab:

1. Create a Compute Engine virtual machine using the Google Cloud Platform

2. Create a Compute Engine virtual machine using the gcloud command-line interface.

3.Connect between the two instances



## Steps involved
  1. Create a Compute Engine virtual machine using the Google Cloud Platform (GCP) Console.

       gcloud compute instances create my-vm-1  --machine-type "ni-standard-1" --image-project "debian-cloud" --image "debian-9-strecth-v20190213" --subnet "default" --tags http

  2. Create a Compute Engine virtual machine using the gcloud command-line interface.

      gcloud config set compute/zone us-central1-b

      gcloud compute instances create my-vm-2  --machine-type "n1-standard-1"  --image-project "debian-cloud"  --image "debian-9-stretch-v20190213" --subnet "default"


  3. Connect between the two instances.

      1. Use the ping command to confirm that my-vm-2 can reach my-vm-1 over the network:

          - Connect to my-vm-2:

            gcloud compute ssh my-vm-2

          - ping my-vm-1 from my-vm-2:

             ping -c 4 my-vm-1

          - Use the ssh command to open a command prompt on my-vm-1 from my-vm-2:

             ssh my-vm-1

          - At the command prompt on my-vm-1, install the Nginx web server:

             sudo apt-get install nginx-light -y

          - Use the nano text editor to add a custom message to the home page of the web server:

            sudo nano /var/www/html/index.nginx-debian.html

          - Add text like, and replace YOUR_NAME with your name:  

            Hi from Isaac Owusu

           - Exit the editor and confirm that the web  server is serving your new page. At the command prompt on my-vm-1, execute this command:

             curl http://localhost

            - The result:

                         The response will be the HTML source of the web server's home page, including your line of custom text.

            - To exit the command prompt on my-vm-1, execute this command:

              Exit

            - Get the external IP of the my-vm-1 instance from this command:

              cloud compute instances list  --zone  us-central1a
