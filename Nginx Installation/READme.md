# Nginx Installation and setup:

- Prerequisite: AWS Account.

-  Create Security Group and open Required ports 8080
  
- Create redhat ec2 t2.medium Instance with 4GB of RAM.

- Attach Security Group to ec2 Instance.

# Nginx - HTTP Server Installation:
# set hostname as ngnix and because the root user

```bash
sudo hostname ngnix
sudo su -
```

# Install Nginx in redhat as root user

```bash
dnf install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
```

```bash
yum install -y nginx
```

# Enable the nginx service

```bash
systemctl enable nginx
```

# Start the nginx service
```bash
systemctl start nginx
```

# Check the nginx service status
```bash
systemctl status nginx
```
# Access nginx web -  
using publicIP:80

# Rename default nginx config file - for backup purpose:
```bash
sudo mv /etc/nginx/nginx.conf /etc/nginx/nginx.conf.bkp
```

# Create nginx config file in default path and define proxy(reverse proxy) rules.
```bash
sudo tee /etc/nginx/nginx.conf > /dev/null << EOF
events {
    worker_connections 1024;
}

http {
    keepalive_timeout 5;

    upstream tomcatServers {
        keepalive 50;
        server 172.31.32.211:8090;
        server 172.31.35.241:8080;
        server 172.31.41.137:8080;
    }

    server {
        listen 80;

        location / {
            proxy_set_header  X-Real-IP \$remote_addr;
            proxy_set_header  X-Forwarded-For \$proxy_add_x_forwarded_for;
            proxy_set_header  X-Forwarded-Proto \$scheme;
            proxy_set_header  Host \$host;
            proxy_pass http://tomcatServers;
        }
    }
}
EOF
```

# Validate the nginx.conf using the following command
```bash
sudo nginx -t
```

# Reload configurations

```bash
sudo nginx -s reload
```

# Restart nginx Service to reflect the proxy rules.
```bash
sudo systemctl restart nginx
```

# Nginx installation completed:
-----------------------------------
- Access nginx web again by using the below:
- using publicIP:80

# Remove Security-Enhanced Linux (SELinux) 
- Security-Enhanced Linux (SELinux) is a Linux kernel security module designed to provide advanced access control and confinement for Linux systems. It grants administrators greater control over system access, enhancing overall security. However, there are instances where SELinux might hinder certain operations, such as Nginx's ability to establish outbound connections.
- Run the below command:
  
```bash
setsebool -P httpd_can_network_connect true
sudo systemctl restart nginx
```
