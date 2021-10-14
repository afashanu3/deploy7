### Documentation


# Table of Contents
- Docker commands in Terminal
- Github
- AWS 
- Ubuntu  
- Jenkins
- Docker Hub
- Issues


# Docker Commands

Within terminal create image and connect it ECS and push it to AWS

Using these commands found located in push commands tab

```
aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/--------
docker build -t jenkins .
docker images
docker tag jenkins:latest public.ecr.aws/--------/jenkins:latest
docker push public.ecr.aws/--------/jenkins:latest
```





Create a repository


After repository is created 
Select repository and select view push commands 
Add commands into terminal to push image onto aws ECS

![image](https://user-images.githubusercontent.com/84725239/137370150-5c98989d-c8db-47a9-a0d5-c1ed06868a00.png)

After creating a ubuntu instance 

Next enter terminal and go to folder with key
Then
-ssh -i newkey.pem.txt ubuntu@100.26.202.255


￼![Screen Shot 2021-10-13 at 9 09 57 AM](https://user-images.githubusercontent.com/84725239/137374723-9f735a32-c650-4524-838d-f37e58e6c650.png)

First go to the ECS and create a cluster

￼

Networking only will be the first tab selected 
Give this cluster a name and didn’t configure a vpc(used default)

![Screen Shot 2021-10-13 at 9 09 03 AM](https://user-images.githubusercontent.com/84725239/137374803-79523cc7-7afe-405e-917a-47daf27121cb.png)

![Screen Shot 2021-10-13 at 9 08 55 AM](https://user-images.githubusercontent.com/84725239/137374822-0e169f37-0394-4dd7-95a5-7074176b8549.png)

￼
￼
Next go to the task definition tab and create a new task definition and select Fargate


![Screen Shot 2021-10-13 at 9 09 37 AM](https://user-images.githubusercontent.com/84725239/137374790-3c84a144-9510-49f2-8b8f-fc4a680557df.png)


Then after creating the task definition


These were the specific configurations needed


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

Download recommended plugins and 

- Docker pipeline plugin

- AWS EC2 plugin


![Screen Shot 2021-10-11 at 11 41 09 PM](https://user-images.githubusercontent.com/84725239/137374956-e692f2be-2ee8-455c-b809-2982d43a2f25.png)



Input Credentials 

For Docker 

Ubuntu SSH

Github (personal token needed)


Within the folder that contains the snapshot
Drag file to GitHub demo-0.0.1-SNAPSHOT.jar 

# Ubuntu

In ubuntu vm instance
```
-curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

-sudo apt-get install unzip

-sudo apt update

-sudo apt install default-jdk

-sudo ./aws/install

-sudo apt-get unzip awscliv2.zip

-unzip awscliv2.zip

-aws configure

-pwd

```


```
-sudo apt update


-sudo apt install software-properties-common ca-certificates curl gnupg-agent apt-transport-https


-curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

-sudo add-apt-repository \ "deb [arch=amd64] https://download.docker.com/linux/ubuntu \ $(lsb_release -cs) \ stable"

-sudo apt update 

-sudo apt install docker-ce docker-ce-cli containerd.io

```

# Jenkins
 
Configure Jenkins agent
After assign label given to agent to jenkinsfile on github
Within Jenkinsfile add commands 
Multibranch pipeline 
Build 
Successful test 


![Screen Shot 2021-10-11 at 11 37 55 PM](https://user-images.githubusercontent.com/84725239/137375104-ea192c64-b822-4910-8e00-ba472fd5547b.png)
![Screen Shot 2021-10-14 at 2 30 17 PM](https://user-images.githubusercontent.com/84725239/137375458-30dbb911-362a-45c8-b702-d3ecba76e8ab.png)


Test was broken to see how certain aspects of code work 
