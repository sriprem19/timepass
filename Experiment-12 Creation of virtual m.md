Experiment-12: Creation of virtual machine for Ubuntu OS and Deploying 
the web application 
1. Creation of virtual machine 
Using Amazon EC2 eliminates your need to invest in hardware up front, so you can develop and deploy 
applications faster.  
Ex : Launch ubuntu instnace 
Step 1: Login to AWS /canvas account 
Step 2: Services --  EC2 
Step 3: Choose region which is near ?   
Services -- EC2 --- Launch Instance  
Stage 1  --Name (Giving name to the machine) ubuntu 
Stage 2  -- Select AMI  ( Note: Select free tier eligible ) ubuntu server 
Stage 3   --  Architecture as 64-bit
Stage 4  --  Instance type ----  t2.micro(default 1 CPU,1 GB RAM) 
 Stage 5  --  Create a new keypair---a keypair will downloaded  with extension .pem
  Store key in folder AWS 
Stage 6  -- Network Setting ----Create Security group  --  ( It deals with ports ) 
 (Note for understanding We have 0 to 65535 ports. Every port is dedicated to special purpose) 
  
Do this step : HERE select http and https 
   Stage 7 -- Storage - 8GB ( Observation - we have root - it is same as C Drive) 
         Stage 8 --- click on launch instance 
    Stage 9: Number of instances ---1 
Observation - One machines created
Do this step:---once it is created select that instance and click on connect 
Here copy the ssh – i command from SSH client connect tab 
We can use powershell /gitbash /webconsole , to connect to ubuntu machine.
To connect to above terminals we need to go into the path of the keypair.and  
paste  the 
ssh -i command from the aws console

2.Deploying the web application using Nginx and Tomcat servers 
.Clone the application from github, Write the Dockerfile 
once connected to instance 
Step 1:-  install the docker 
sudo apt update
sudo apt-get install docker.io 
sudo apt install git
install docker ---apt-get update - 
apt-get install docker.io
apt-get install nano
Step 1: Create basic index.html file in folder Example and save it
step 2:-  git clone <paste the github link of web 
 project> 
step 3:- navigate to the aws 
create Dockerfile in above command prompt in ububtu ie in power shell 
        Nano Dockerfile
FROM nginx:alphine
COPY ./usr/share/nginx/html
 
Step :  Build docker image by executing the following command 
                sudo docker build –t mywebapp .
Thus image is created 
 
Step :  run the image and map it to port 80  
  sudo docker run –d –p 80:80 mywebapp 

2 MAVEN WEB PROJECT DEPLOYMENT IN AWS 
Click on start lab
Click on AWS
Click on EC2 
Click on launch instance
Give name 
Create new key 
maven rsa .pem 
Check all the boxes under network and click  on launch instance 
Click on instances 
Wait until you get 1 test passes
Click on connect after checking the box 
Copy ssh command 
Open the terminal, Navigate to the path 
sudo apt-get update 
sudo apt-get install docker.io
sudo apt install git 
sudo apt install nano
Open MAVEN WEB PROJECT REPO in github and copy http link
git clone https://github.com/HARIVIGNESHRAO/se.git
ls 
cd se
ls
nano Dockerfile
FROM tomcat:9-jdk11
COPY target/* .war/usr/local/tomcat/webapps
sudo docker build -t maven 
sudo docker run -d -p 80:8080 maven
Open MAVEN WEB PROJECT REPO in github and copy http link
Paste it in the browser to get below output 
Note : if https :__ won’t work then type just http:___ 
