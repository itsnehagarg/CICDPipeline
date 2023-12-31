# CI CD Pipeline
Setting up CI CD complete Pipeline

### Install Java

``
wget https://download.java.net/java/GA/jdk13.0.1/cec27d702aa74d5a8630c65ae61e4305/9/GPL/openjdk-13.0.1_linux-x64_bin.tar.gz
``

``
tar -xvf openjdk-13.0.1_linux-x64_bin.tar.gz
``

``
mv jdk-13.0.1 /opt/
``

Step 2: Setting JAVA_HOME and Path Environment Variables

Open .profile file from the home directory and add the following lines to it.

``
JAVA_HOME='/opt/jdk-13.0.1'


PATH="$JAVA_HOME/bin:$PATH"


export PATH

``

### Install Maven
``
sudo apt install maven
``
### Git clone the Spring Boot repo
git clone https://github.com/itsnehagarg/SpringBootApplication.git

### Create a jar file
mvn clean package

### Run the jar file
java -jar target/NewProjectSpringBoot-0.0.1-SNAPSHOT.jar

### Access the application on localhost
http://localhost:8080/

### We have executed the Spring Boot application successfully!

## let's Dockerize the Spring Boot application

### Create a docker file Dockerfile
FROM openjdk:8-jdk-alpine

WORKDIR /opt/app

COPY target/NewProjectSpringBoot-0.0.1-SNAPSHOT.jar app.jar

ENTRYPOINT ["java","-jar","app.jar"]

### Build the Docker Image:


``docker build -t newapp:v1 .
``

``
docker run -d -p 8010:8080 -t newapp:v1
``

#### Application is available on: 

http://<ip-address>:8010

![image](https://github.com/itsnehagarg/CICDPipeline/assets/20385826/2a2b7933-ee1a-41ad-ae62-32ae4a743e6d)


## Step 2: Install Jenkins

``
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
  
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
  
sudo apt-get update

sudo apt-get install jenkins

``
## Step 6: Enable the Jenkins service to start at boot:

```sh 
sudo systemctl enable jenkins
```

## Step 7: Start Jenkins as a service:

```sh 
sudo systemctl start jenkins
```

## Step 8: You can check the status of the Jenkins service using the command:

```sh 
sudo systemctl status jenkins
```
## To check if the jenkins is running

ps -ef | grep jenkins

## Step 9: Access Jenkins

http://localhost:8080


![image](https://github.com/itsnehagarg/CICDPipeline/assets/20385826/b0f833be-38e3-4906-889e-6e573d893609)



