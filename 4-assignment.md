# Task to be Performed:
1. Trigger a pipeline using Git when push on develop branch
2. Pipeline should pull Git content to a 

### We are going to do this assignment on AWS.
 Create 2 instances one for master machine where we are going to install Jenkins and Java and second one is slave machine where we wil install Java .

### install Java 
sudo apt update
sudo apt install openjdk-17-jdk
java --version

Now we are going to install jenkins on aur Master Machine.
We are going to install the jenkins by Script file

```hcl
sudo nano a.sh

sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt update
sudo apt install jenkins-y

### Run:
bash a.sh
jenkin --version
```
### Copy the  Public IP of Master Mchine and past to the browser  with port 8080.
```hcl
Example:   http://<publicip>:8080

sudo cat /var/lib/jenkins/secrets/initialAdminPassword

```
Open the key and paste it to the jenkin dashboard. 
You will be redircted to the jenkin dashboard and enter the credintial asking.

After login into the jenkins dashboard we need to create a machine as a slave. For that we need to create a node. 
For creating new node we need to go to the setting first then click on node.

After Creating the node we need to create a develop branch into our repo main branch.

Go to the Jenkins dashboard and click on the new item.

```hcl
Name of Item ====> Freestyle project =====> Save
```


Because we want to trigger the github for that we need to past the project url into the jekin new item.
```hcl
General==>github project==>paste the github project url

```hcl
Create a Jenkins Pipeline Job

Go to Jenkins dashboard.

New Item

Enter name:
assign-1-pipeline

Select:
Pipeline
Click OK.

Configure GitHub repository:
Inside job configuration:
Scroll to Pipeline → Definition

Select:
Pipeline script from SCM

SCM:
Git

Repository URL:
https://github.com/Kunwar-Utpal-Singh/assign-1.git

Branch:
*/develop

Save.
Configure job to run on Slave Machine:

Inside job configuration find:
Restrict where this project can run
Enter the label of your agent.

Example:
jenkins-slave-machine

This tells Jenkins:
Run this job on the slave machine

Enable webhook trigger:
In the same job configuration check:

GitHub hook trigger for GITScm polling

Save the job.

Create webhook in GitHub
Go to your repo on GitHub.

Settings
 → Webhooks
 → Add webhook

Fill:

Payload URL
http://<jenkins-public-ip>:8080/github-webhook/

Example:

http://3.110.xx.xx:8080/github-webhook/

Important: ending slash is required
/github-webhook/

Content type:
application/json

Events:
Just the push event

Click:
Add webhook
=================
git add .
git commit -m "trigger pipeline"
git push origin develop

now thw flow is :
GitHub → webhook → Jenkins → pipeline → slave machine
```


# Now click on build:
You will see build is successfull.
After this only we have created a pipeline Successfully.
For confirmation go to the Slave machine and run ls you will see the file with  name "Jenkins".
```hcl
cd jenkins======> ls========> cd workspace
```
 you will see the Job you have creaed on jenkins dashboard.

 Now anything you are changing on develop github branch its automatically trigger the jenkins pipeline and job will be created automatically on jenkins.



