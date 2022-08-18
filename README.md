# Projec9-CI-Pipeline
Continuous Integration Pipeline For Tooling Website

This projects starts with the creation of EC2 instance running Ubuntu Server 20.4:\
<img width="761" alt="Jenkins Instance" src="https://user-images.githubusercontent.com/61512079/185502943-4ed56ab1-5839-4393-b680-28c14e00b778.PNG">

Next is the Installation of JDK (since Jenkins is a Java-based application):\
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

