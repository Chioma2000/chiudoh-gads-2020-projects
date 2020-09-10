# LAB: Google Cloud Fundamentals: Getting Started with App Engine
# Objectives: 
In this lab, you will learn how to perform the following tasks

-Initialize App Engine.

-Preview an App Engine application running locally in Cloud Shell.

-Deploy an App Engine application, so that others can reach it.

-Disable an App Engine application, when you no longer want it to be visible.

# Steps:

**Task 1: Initialize App Engine**

#Initialize your App Engine with your project and choose its region:

gcloud app create --project=$DEVSHELL_PROJECT_ID

#Clone the source code repository for a sample application in the hello_world directory:

git clone 
https://github.com/GoogleCloudPlatform/python-docs-samples  

#Navigate to the source directory

cd python-docs-samples/appengine/standard_python3/hello_world
 
**Task 2: Run Hello World application locally
**

#Download and update the packages list

sudo apt-get update

#Set up a Python virtual environment in which you will run your application

sudo apt-get install virtualenv

If prompted [Y/n], press Y and then Enter

virtualenv -p python3 venv

#Activate the virtual environment

source venv/bin/activate

#Navigate to the Project directory and install dependencies

pip install -r requirements.txt

#Run the Application

python main.py

Please ignore the warning if any.

press Ctrl+C to abort the deployed service.

**Task 3: Deploy and run Hello World on App Engine 
 **

#Navigate to the source directory
 
cd ~/python-docs-samples/appengine/standard_python3/hello_world

#Deploy your Hello World Application

gcloud app deploy

If prompted "Do you want to continue (Y/n)?", press Y and then Enter.

#Launch your browser to view the app

gcloud app browse

Copy and paste the URL into a new browser window.


**Task 4: Disable the application
**

If you'd like to disable the app you just deployed, go to 

App Engine on Console and select Settings > Application Settings > Disable Application.
