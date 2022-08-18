# Projec9-CI-Pipeline
Continuous Integration Pipeline For Tooling Website

This projects starts with the creation of EC2 instance running Ubuntu Server 20.4:\
<img width="761" alt="Jenkins Instance" src="https://user-images.githubusercontent.com/61512079/185502943-4ed56ab1-5839-4393-b680-28c14e00b778.PNG">

Next is the Installation of JDK (since Jenkins is a Java-based application):
```bash
sudo apt update
sudo apt install default-jdk-headless
```
<img width="542" alt="JDK" src="https://user-images.githubusercontent.com/61512079/185503027-99311501-9fe7-47f5-a57a-24060a063b6b.PNG">

After the JDK is installed successfully,  we update and install Jenkins with the set of commands below:
```bash
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > \
    /etc/apt/sources.list.d/jenkins.list'
sudo apt update
sudo apt-get install jenkins
```

<img width="722" alt="Jenkins-Install" src="https://user-images.githubusercontent.com/61512079/185503280-2f89b1f1-e303-4a30-90b9-6101c908b4c3.PNG">

Jenkins is confirmed up and running as follow:
```bash
sudo systemctl status jenkins
```
<img width="947" alt="Jenkins - Status" src="https://user-images.githubusercontent.com/61512079/185503513-d9cd4f3a-5916-49ff-862e-6bfd50ba355a.PNG">

Next we open TCP port 8080 on the EC2 instance since that is the default port for Jenkins:
<img width="708" alt="TCP8080" src="https://user-images.githubusercontent.com/61512079/185504238-a28392b3-741a-49cd-99d9-2f880ad1d9a2.PNG">

To perform the initial Jenkins setup, open the link on the browser as follow:
```http
http://<Jenkins-Server-Public-IP-Address-or-Public-DNS-Name>:8080
```
<img width="749" alt="Jenkins-Page" src="https://user-images.githubusercontent.com/61512079/185504851-42766b67-76e5-44df-b254-7156830f697c.PNG">

To get the default Jenkins password, run the command below:
```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
After we input the generated password, we have the page shown below:\
<img width="752" alt="Jenkins-Logon" src="https://user-images.githubusercontent.com/61512079/185505234-31dfaaae-91d1-4d13-9aa0-8c573c51d8ee.PNG">

We are prompted to pick the plugin to install, so we select "Install Suggested plugins".
After the plugin installation is complete, we are prompted to create admin user as follow:\
<img width="687" alt="Jenkins User Create" src="https://user-images.githubusercontent.com/61512079/185505644-26a1f305-a598-4536-8d40-23a0a9505216.PNG">

<img width="440" alt="jenkins complete" src="https://user-images.githubusercontent.com/61512079/185506207-1899189f-faa0-4d90-bbb4-a2d0449cba70.PNG">

The next step in the project is to configure Jenkins to retrieve source codes from GitHub using Webhooks. First we enable webhooks in the GitHub repository settings.



