# Whenever you are installing an application in Linux server, always install it in the/opt - directory

#Tomcat Installation and Configuration Guide:

```bash
https://tomcat.apache.org/download-90.cgi
```

```bash
https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.79/bin/apache-tomcat-9.0.79.zip
```

#Tomcat, a widely used web server and servlet container can be easily installed and configured for your Java web applications. Follow these steps to get Tomcat up and running on your system.

#!/bin/bash

# Prerequisites

- AWS Account
  
- Ubuntu t2.micro Instance
  
- Security Group with required ports open
  
- Java OpenJDK 1.8+ installed
  

# Change the hostname to 'tomcat'
```bash
sudo hostnamectl set-hostname tomcat
sudo su - ubuntu
sudo apt update
```

# Install required packages

```bash
cd /opt
sudo apt install git wget unzip -y
sudo apt install openjdk-11-jdk 
```

# Download and extract Tomcat 9.0.75

```bash
sudo wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.79/bin/apache-tomcat-9.0.79.zip
sudo unzip apache-tomcat-9.0.79.zip
sudo rm -rf apache-tomcat-9.0.79.zip
```
# Rename Tomcat directory
```bash
sudo mv apache-tomcat-9.0.79 tomcat9
```

# Set permissions and ownership
```bash
sudo chmod 777 -R /opt/tomcat9
sudo chown ubuntu -R /opt/tomcat9
```

# Start Tomcat
```bash
sh /opt/tomcat9/bin/startup.sh
```

# Create symbolic links for managing Tomcat as a service
```bash
sudo ln -s /opt/tomcat9/bin/startup.sh /usr/bin/starttomcat
sudo ln -s /opt/tomcat9/bin/shutdown.sh /usr/bin/stoptomcat
```

# Start Tomcat using the service links
```bash
starttomcat
```

# Switch back to 'ubuntu' user
```bash
sudo su - ubuntu
```
-----------------------------------------------------------------------------------------------
# Remember to make the script executable before running it:
```bash
chmod +x script_name.sh
```

- Replace script_name.sh with the desired name for your script file. After that, you can run the script by executing ./script_name.sh in the terminal.
