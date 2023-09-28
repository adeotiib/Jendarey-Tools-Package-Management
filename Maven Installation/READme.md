# Apache Maven Installation And Setup In AWS EC2 Ubuntu Instance:

# Prerequisite:
-AWS Account.

-Create Security Group and open Required ports 22

-Create ubuntu ec2 t2.medium Instance with 4GB of RAM.

-Attach Security Group to ec2 Instance.

-Install java openJDK 11 and 17 


# Install Apache Maven on Ubuntu 22.04 - Using package manager:

-Install Java JDK 11+ and other software (Git, wget, and tree):

# Step 1: Change the hostname to Maven
~~~
sudo hostnamectl set-hostname maven
sudo su - ubuntu
~~~
# Step 2: Update system repositories
~~~
sudo apt update
~~~
# Step 3: Upgrade installed packages
~~~
sudo apt upgrade -y
~~~

# Step 4: Install dependencies
~~~
sudo apt install tree git openjdk-17-jdk openjdk-11-jdk -y
~~~

# Step 5: Install Maven
~~~
sudo apt install maven -y
~~~

# Step 6: Verify Maven installation
~~~
mvn -version
~~~

# Display Java and Git versions
~~~
java -version
~~~

~~~
git --version
~~~


=====================================================================
# Install Apache Maven on Ubuntu 22.04 - Using Manual method
# Install Java JDK 11+ and other software (GIT, wget, and tree):

```bash
sudo hostnamectl set-hostname maven
sudo su - ubuntu
sudo apt update
cd /opt
sudo apt install wget nano tree unzip git -y
sudo apt install openjdk-11-jdk openjdk-17-jdk -y 
java -version
git --version
```

# Download, extract, and Install Maven:
```bash
sudo wget https://dlcdn.apache.org/maven/maven-3/3.9.4/binaries/apache-maven-3.9.4-bin.zip
sudo unzip apache-maven-3.9.4-bin.zip
sudo rm -rf apache-maven-3.9.4-bin.zip
sudo mv apache-maven-3.9.4/ maven
```

# Set Environmental Variable - For Specific User eg ubuntu:
```bash
vi ~/.bash_profile  # and add the lines below
export M2_HOME=/opt/maven
export PATH=$PATH:$M2_HOME/bin
```

# Refresh the profile file and Verify if Maven is running:
```bash
source ~/.bash_profile
mvn -version
```


--------------------------------------------------------------

#Install through Bash Script - user data:

#!/bin/bash

# Change hostname

sudo hostnamectl set-hostname maven

# Update and install basic software

sudo apt update

sudo apt install wget nano tree unzip git openjdk-11-jdk -y

# Switch to the ubuntu user

sudo su - ubuntu

# Download, extract, and install Maven

cd /opt

sudo wget https://dlcdn.apache.org/maven/maven-3/3.9.4/binaries/apache-maven-3.9.4-bin.zip

sudo unzip apache-maven-3.9.4-bin.zip

sudo rm -rf apache-maven-3.9.4-bin.zip

sudo mv apache-maven-3.9.4/ maven

# Set Environmental Variable for specific user (ubuntu)

echo 'export M2_HOME=/opt/maven' >> ~/.bash_profile

echo 'export PATH=$PATH:$M2_HOME/bin' >> ~/.bash_profile

# Refresh the profile

source ~/.bash_profile
 
----------------------------------------------------------------

# Verify Maven installation

mvn -version

# Display Java and Git versions

java -version

git --version


