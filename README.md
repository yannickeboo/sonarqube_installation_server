# sonarqube_installation_server
# 1- Install depencies
```
apt update -y
apt install openjdk-11-jre-headless -y
apt install openjdk-11-jdk-headless -y
```
## check java version
```
java --version
```
# 2 Install Sonarqube
## go to : https://www.sonarqube.org/downloads/ and then click on download for free
## then ![image](https://user-images.githubusercontent.com/85393914/169076597-f7e6fe5a-d3a8-41c4-b1f6-ba7a76e8f818.png)
### right click on click here and copy the copy the link address

```
cd /opt
wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.4.0.54424.zip
apt install unzip -y
```
```
unzip sonarqube-9.4.0.54424.zip
```
# 3- Starting Sonarqube
## Note , it is good to start sonarqube as root user because it uses elastic search
```
cd sonarqube-9.4.0.54424/bin/linux-x86-64#
vim sonar.sh
```
## look for this line
  ![image](https://user-images.githubusercontent.com/85393914/169082168-b1a292ae-a73b-4863-89f5-3bf372f51037.png)

## put a normal user
![image](https://user-images.githubusercontent.com/85393914/169082483-d29af5cd-6f81-4576-aa14-6eef98adaaf4.png)
## save it
## Let'schange the ownership of few files  to the new user(for example the new user is yannick)
```
chown -R yannick:yannick /opt/sonarqube-9.4.0.54424/
```
# let's start sonarqube now
```
cd sonarqube-9.4.0.54424/bin/linux-x86-64#
sh sonar.sh start
sh sonar.sh status
```
# sometime, we may need to open port on ubuntu server
```
sudo ufw status
sudo ufw enable
sudo ufw allow 9000/tcp
sudo ufw reload
```
# 4- Access Sonarqube 
## use the ipaddress:9000
