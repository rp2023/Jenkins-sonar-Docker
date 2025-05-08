# Jenkins-sonar-Docker
Ref:https://youtu.be/361bfIvXMBI?si=Mi5moyt5iuHE7Tzp

Step-0: Create/Launch 3 Ec2 Ubuntu VM (t2.medium)
==========================
Install Jenkins in first machine ,Docker second VM and sonarqube in third machine.

Step-01: Jenkins install:
=========================
  Login first machine unising gitbash & install Jenkins step by step as below.
  step-1.1: Enable 8080 Port Number in Security Group Inbound Rules:
 
step-1.2: Install java:
========================= 
     sudo apt update
     sudo apt install fontconfig openjdk-17-jre
     java -version
  
step-1.3: Install Jenkins:
========================
   sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
    https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
   echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null
    sudo apt-get update
    sudo apt-get install jenkins
    
step-1.4: Start Jenkins:
========================
   sudo systemctl enable jenkins
   sudo systemctl start jenkins
  
step-1.5: Verify Jenkins:
===================
   sudo systemctl status jenkins
   
step-1.6: Open jenkins server in browser using VM public ip:
======================
   http://public-ip:8080/
   
step-1.7: Copy jenkins admin pwd:
===============================
   sudo cat /var/lib/jenkins/secrets/initialAdminPassword
   
step-1.8: Create Admin Account & Install Required Plugins in Jenkins:
========

Step-02 Install and start Sonarqube:
================================
Login second VM and change its hostname
  sudo hostnamectl set-hostname Soarqube
  
step-2.2: Go to sonar website
=======================
 https://www.sonarsource.com/products/sonarqube/downloads/
 Right click on download community edition and copy link
 wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-25.5.0.107428.zip
 step-2.3: Unzip the sonarqube file
  sudo apt install unzip 
  sudo unzip <zip.file>
  
  step-2.4: Start the sonar server
  =============================
  cd sonarqube-9.0.9/
  cd bin
  ls
  cd linux-x86-64
  ls
  sonar.sh
  ./sonar.sh
  sonar.sh {start|stop|force stop| console|restart|status|dump}
  
  step-2.5: enable inbound 9000 port number in security group
  =================================================
  https://public-ip:9000 
   Default usr:admin, pass:admin.

   Step-03 Install docker 
   ==========================
  step-3.1:Login in Third VM using gitbash & change its hostname
  sudo hostnamectl set-hostname docker
  sudo apt update -y
  sudo apt install docker.io -y
  sudo systemctl start docker
  sudo usermod -aG docker ubuntu
  docker -v
  

    



   
