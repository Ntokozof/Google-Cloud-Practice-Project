# Google-Cloud-Practice-Project
Google Cloud Practice Project


In this project you will find 15 screen short of the Qwik Labs (qwiklabs) that I did.
There are also two files containing selected labs from Console instructions to 100% command line instructions.
This are Google Cloud Fundamentals - Getting Started with Compute Engine.txt 
And Google Cloud Fundamentals - Getting Started with App Engine.txt files

The contents of these file is also found below.




# Google Cloud Fundamentals: Getting Started with Compute Engine
I.	First I create 2 VM’s my-vm-1 and my-vm-2 in the region us-central1 and zones us-central1-a and us-central1-b respectively <br>
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
VII.	I then Edited the h(1) tag To Hi from Felix. I saved and exited the file by  Ctrl+O, Enter and Ctrl+X
VIII.	Used curl http://localhost/ to view the changes, which shows the web server’s home page
IX.	I exited command prompt for my-vm-1 by exit and I was on the command prompt for my-vm-2 
X.	I Used curl http://my-vm-1/ to see if I can still reach my-vm-1 web server from my-vm-2 instance, the result shows the web server’s(HTML source) home page of my-vm-1 instance.
XI.	In the Google platform console Compute Engine -> VM instances page I copied the External IP address for my-vm-1 instance and past is in the browser tab and the web server was accessible. 


# Google Cloud Fundamentals: Getting Started with App Engine

## The objective of the lab was the following
•	Initialize App Engine.
•	Preview an App Engine application running locally in Cloud Shell.
•	Deploy an App Engine application, so that others can reach it.
•	Disable an App Engine application, when you no longer want it to be visible.

I.	In GCP console I opened Cloud Shell.

II.	In the Cloud Shell I used gcloud auth list command to view active account names.

III.	I list the project ID using command gcloud config list project 

IV.	To initialize App Engine in my project I used the command                                                           gcloud app create –project=$DEVSHELL_PROJECT_ID

V.	I Cloned the source code repository for a sample application                                                               git clone https://github.com/GoogleCloudPlatform/python-docs-samples

VI.	I navigate to the source directory                                                                                                                cd python-docs-samples/appengine/standard_python3/hello_world

VII.	To download and update the packages list I ruined the command                                                 sudo apt-get update

VIII.	To set up a virtual environment where I run the application I used the following command.                                                           sudo apt-get install virtualenv                                
virtualenv -p python3 venv

IX.	To activate the virtual environment I used the command.
source venv/bin/activate

X.	Then I navigated to the project directory and installed dependencies with the command.
pip install  -r requirements.txt

XI.	To run the python application I used the command
python main.py

XII.	In Cloud Shell, click Web preview, Preview on port 8080 to preview the application.

XIII.	To end the test, in Cloud Shell I exicuted Ctrl+C.

XIV.	Using the Cloud Console, verify that the app is not deployed. In the Cloud Console, on the Navigation menu, click App Engine > Dashboard.

XV.	To get back to the source directory so I can be able to deploy the app I used the command:
cd ~/python-docs-samples/appengine/standard_python3/hello_world

XVI.	To deploy application I used.                                                                                                                gcloud app deploy 

Do you want to continue yes and enter as prompted.

XVII.	To launch the browser and view the app I used                                                                                  
gcloud app browse


XVIII.	The app can be viewed in the browser at                                     http://YOUR_PROJECT_ID.appspot.com

XIX.	To undeploy the app under App Engine -> settings I clicked Disable application, enterd the App ID and clicked DISABLE the app is no longer available at http://YOUR_PROJECT_ID.appspot.com in the browser.


