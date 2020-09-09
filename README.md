# Google-Cloud-Practice-Project
Google Cloud Practice Project


<b>Google Cloud Fundamentals: Getting Started with Compute Engine<b>
I.	First I create 2 VM’s my-vm-1 and my-vm-2 in the region us-central1 and zones us-central1-a and us-central1-b respectively 
gcloud compute zones list | grep us-central1
gcloud config set compute/zone us-central1-a
gcloud compute  instances create “my-vm-1” \ -- machine-type “n1-standaed-1” \ --image-project “debian-cloud” \ --image “debian-9-stretch-v20190213” \ --subnet “default”

gcloud compute zones list | grep us-central1
gcloud config set compute/zone us-central1-b
gcloud compute  instances create “my-vm-2” \ -- machine-type “n1-standaed-1” \ --image-project “debian-cloud” \ --image “debian-9-stretch-v20190213” \ --subnet “default”

II.	I open the command prompt for my-vm-2 instance by clicking SSH of VN instance.
III.	I use the command ping my-vm-1 from my-vm-2 SSH then Ctrl+C to abort the ping command.
IV.	Within the SSH window of my-vm-2 I SSH my-vm-1 using the command ssh my-vm-1
V.	I used sudo apt-get install nginx-light –y to install the Nginx web server in my-vm-1 instance.
VI.	To add a custom message to the home page of the web server I used sudo nano /var/www/html/index.nginx-debian.html
VII.	I then Edited the <h1> tag To Hi from Felix. I saved and exited the file by  Ctrl+O, Enter and Ctrl+X
VIII.	Used curl http://localhost/ to view the changes, which shows the web server’s home page
IX.	I exited command prompt for my-vm-1 by exit and I was on the command prompt for my-vm-2 
X.	I Used curl http://my-vm-1/ to see if I can still reach my-vm-1 web server from my-vm-2 instance, the result shows the web server’s(HTML source) home page of my-vm-1 instance.
XI.	In the Google platform console Compute Engine -> VM instances page I copied the External IP address for my-vm-1 instance and past is in the browser tab and the web server was accessible. 

