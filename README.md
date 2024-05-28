                
# Jenkins-setup                 

## step -1                   
Lunch the EC2 instance "Amazon Linux, Ubuntu"                   
       
## step -2            
During create the the ec2 instance setup the SG (security group) and open the port 8080 (this port use for the jenkins)
                                     
## step -3            

## sudo su -    
## sudo  apt-get update                                   
     
And Lunch the server and Update the server

## step -4


## sudo apt install default-jre   

After update the server now we need to install java on the server 

## step -5    
    
## sudo apt install jenkins

Now we install the  jenkins 

## step -6 

## wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
## sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'

Add Jenkins Repository Key and Source

## step -7

## sudo systemctl start jenkins    
## sudo systemctl status jenkins

Start the jenkins server and  check the status 

## step -8 

Access the jenkins help of your public IP

## 54.123.456.789:8080

After connect with the jenkins then, jenkins ask the password then we can use the " copy the location they already give in the jenkins page"

Come to the server and
## cat /copy/the/location/of/the/path/we/have/

Then we get the password and use can use the password in jenkins

## Then we can use the jenkins 

# create the CICD pipeline

Cleck the "New Item" Give the name of your Item or new pipeline

## Then the select the pipeline type Like "freestyle project, Pipeline like this"

## Then let we selecte the pipeline then 

## cleck "OK"

## Point add " Description " add some point about the project

## Then add the "Build Trigger"
Like "GitHub hook trigger for GITScm polling"

## Then the add the script for the pipeline 

________________________________________________________________________
pipeline {
    agent any

    stages {
        stage('Copy the code') {
            steps {
                echo 'code is comde'
                git uri: "add there your git repo url", branch: "main/master"       "this is a example line "
            }
        }
        stage('Installing the all requerments') {
            steps {
                echo 'Install the all reruerments of Server'
                sh "python3 -m pip install -r requirements.txt"                     "this is a example line "
            }
        }
        stage('deploy thhe code in server') {
            steps {
                echo 'Deploy the code'
                sh "python3 -m streamlit run App.py"                                 "this is a example line"
            }
        }
    }
}             

_________________________________________________________________

## In this code we connect the jenkins with gitHub
## And it will be use and add the build steps and also and the deployment steps.



## We can do some change in the code.
## Then we can do "Save" and "apply"
## After that we do "Build Now" then we can start the build the pipeline use wee can use it .







