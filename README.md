# Jenkins-sonar-Docker
Ref:https://youtu.be/361bfIvXMBI?si=Mi5moyt5iuHE7Tzp

Step-0: Create/Launch 3 Ec2 Ubuntu VM (t2.medium) 
Install Jenkins in first machine ,Docker second VM and sonarqube in third machine.
Step-01: Jenkins install
- Login first machine unising gitbash & install Jenkins step by step as below.
  step-1.1: Enable 8080 Port Number in Security Group Inbound Rules
  step-1.2: Install java
  
     sudo apt update
     sudo apt install fontconfig openjdk-17-jre
     java -version
  
  3)Install Jenkins:
  
   sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
    https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
   echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
    sudo apt-get update
    sudo apt-get install jenkins
  
4) Start Jenkins:
  
   sudo systemctl enable jenkins
   sudo systemctl start jenkins
5) Verify Jenkins:
   sudo systemctl status jenkins
6) Open jenkins server in browser using VM public ip:
   http://public-ip:8080/
7) Copy jenkins admin pwd:
   sudo cat /var/lib/jenkins/secrets/initialAdminPassword
8) Create Admin Account & Install Required Plugins in Jenkins:

    



   
