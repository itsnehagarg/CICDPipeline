# CI CD Pipeline
Setting up CI CD complete Pipeline

### Install Maven

``
wget https://download.java.net/java/GA/jdk13.0.1/cec27d702aa74d5a8630c65ae61e4305/9/GPL/openjdk-13.0.1_linux-x64_bin.tar.gz
tar -xvf openjdk-13.0.1_linux-x64_bin.tar.gz
mv jdk-13.0.1 /opt/
``
Step 2: Setting JAVA_HOME and Path Environment Variables

Open .profile file from the home directory and add the following lines to it.
``
JAVA_HOME='/opt/jdk-13.0.1'
PATH="$JAVA_HOME/bin:$PATH"
export PATH
``

