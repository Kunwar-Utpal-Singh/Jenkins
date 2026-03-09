# Prerequisites

Minimum hardware requirements:
256 MB of RAM
1 GB of drive space (although 10 GB is a recommended minimum if running Jenkins as a Docker container)

## Recommended hardware configuration for a small team:

4 GB+ of RAM

50 GB+ of drive space

Comprehensive hardware recommendations:

Hardware: see the Hardware Recommendations page

## Software requirements:

Java 21 or later: see the Java Requirements page

Web browser: see the Web Browser Compatibility page

For Windows operating system: Windows Support Policy

For Linux operating system: Linux Support Policy

For servlet containers: Servlet Container Support Policy

# Steps for installing the Jenkins:

## Installation of Java
```hcl
sudo apt update
sudo apt upgrade -y
sudo apt install openjdk-21-jdk -y
java -version
```

## Installation of Jenkins.
```hcl
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt update
sudo apt install jenkins
```


### Start Jenkins
```hcl
sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
```

Jenkins by default runs on port 8080.

### Get Jenkins admin Pasword:
```hcl
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
### Copy the password
And the open the browser
``hcl
http://localhost:8080
```
Select the jenkins  you Prefer and click on start jenkins installation started.
Enter your Credential and copy you local host and save and click on save and finish.You will see something like "JENKINS IS READY"

Thats all for installation of Jenkins on Linux.





