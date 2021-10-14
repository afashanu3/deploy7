Documentation


#Table of Contents

Docker 

within terminal 
Create image and connect it ecs and push it to AWS
Push commands

aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/x3y9c9q7

docker build -t jenkins .
docker images

docker tag jenkins:latest public.ecr.aws/x3y9c9q7/jenkins:latest

docker push public.ecr.aws/x3y9c9q7/jenkins:latest


Drag file to GitHub
demo-0.0.1-SNAPSHOT.jar

￼
Create a repository
After repository is created 
Select repository and select view push commands 
Add commands into terminal to push image onto aws ECS
￼
After creating a ubuntu instance 
Next enter terminal and go to folder with key
Then
-ssh -i newkey.pem.txt ubuntu@100.26.202.255


￼
First go to the ECS and create a cluster

￼

Networking only will be the first tab selected 
Give this cluster a name and didn’t configure a vpc(used default)



￼
￼
Next go to the task definition tab and create a new task definition and select Fargate

￼
Then creating the task definition

Task role selected ECStaskExecutionRole

Task size
Task memory (GB)
4GB

Task CPU (vCPU)
1vCPU

Container definitions
Add container

In image box get from repository the 
repository-url/image:tag

Port mappings
8080 tcp
After task definition is created use the Public ip and attach it to :8080 to get into jenkins

Password to jenkins will be in the logs of the cluster 

Download required plugins 
-
-

Input Crediantals 
For Docker 
Ubuntu SSH
Github (personal 


Drag file to GitHub
demo-0.0.1-SNAPSHOT.jar


In ubuntu vm instance

-curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

-sudo apt-get install unzip
-sudo apt update
-sudo apt install default-jdk
-sudo ./aws/install
-sudo apt-get unzip awscliv2.zip
-unzip awscliv2.zip
-aws configure
-pwd




-sudo apt update -sudo apt install software-properties-common ca-certificates curl gnupg-agent apt-transport-https

-curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

-sudo add-apt-repository \ "deb [arch=amd64] https://download.docker.com/linux/ubuntu \ $(lsb_release -cs) \ stable"

-sudo apt update -sudo apt install docker-ce docker-ce-cli containerd.io

Jenkins
 Configure Jenkins agent
After assign label given to agent to jenkinsfile on github
Within Jenkinsfile add commands 
Multibranch pipeline 
Build 
Successful test 




Test was broken to see how certain aspects of code work 
