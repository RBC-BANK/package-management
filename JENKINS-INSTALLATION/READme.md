#  **<span style="color:green">Landmark Technologies.</span>**
### **<span style="color:green">Contacts: +1437 215 2483<br> WebSite : <http://mylandmarktech.com/></span>**
### **Email: mylandmarktech@gmail.com**



## Jenkins Installation And Setup In AWS EC2 Redhat Instnace.
##### Prerequisite
+ AWS Acccount.
+ Create Redhat EC2 t2.medium Instance with 4GB RAM.
+ Create Security Group and open Required ports.
   + 8080 got Jenkins, ..etc
+ Attach Security Group to EC2 Instance.
+ Install java openJDK 1.8+ for SonarQube version 7.8

SCRIPT FOR INTALLING JENKINS 
#!/bin/bash
# Author: Prof Legah
# date: 25/08/2020
# Installing Jenkins on RHEL 7/8, CentOS 7/8 or Amazon Linux OS
# You can execute this script as user-data when launching your EC2 VM.
sudo timedatectl set-timezone America/New_York
sudo hostnamectl set-hostname jenkins
sudo yum install wget -y
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum upgrade -y
# Add required dependencies for the jenkins package
sudo yum install java-11-openjdk -y
sudo yum install jenkins -y
sudo systemctl daemon-reload
sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
echo "echo of jenkins installation"
sudo su - ec2-user








### Install Java JDK 1.8+ as Jenkins pre-requisit
### Install other softwares - git, unzip and wget

``` sh
sudo hostnamectl set-hostname ci
sudo yum -y install unzip wget tree git
sudo yum install java-11-openjdk -y
```
###  Add Jenkins Repository and key
```sh
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
cd /etc/yum.repos.d/
sudo curl -O https://pkg.jenkins.io/redhat-stable/jenkins.repo
```

## Install Jenkins
```sh
sudo yum -y install jenkins  --nobest
```
# start Jenkins  service and verify Jenkins is running
```sh
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins
```
# Access Jenkins from the browser
```sh
public-ip:8080
curl ifconfig.co 
```
# get jenkins initial admin password
```sh
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

