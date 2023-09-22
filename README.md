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



