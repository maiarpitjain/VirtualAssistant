# VirtualAssistant
Automated menu that provides face authentication to website and features to reduce human interface.

## Setup AWS 

Setup aws __centos7__ instance and configure it with these software installation 

###Make sure you have oppened traffic to all ports and attached instance to static ip

__Install Apache Webserver__

```
yum install httpd
systemctl start httpd
systemctl enable httpd
```

__Install Ansible__
```
yum install ansible -y
```

__Install Docker__
```
yum install docker -y
systemctl start docker 
systemctl enable docker
```

__Install unzip and git__
```
yum install unzip -y
yum install git -y
```

__Clone This Repository__

```
git  clone https://github.com/VirtualAssistant.git
```

__Unzip this__
```
unzip VirtualAssistant.zip -d /var/www
```

__Apache user have sudo Power__ 

* Apache user should have sudo power entry in /etc/sudoers file
```
apache ALL=(ALL) NOPASSWD: ALL
```

__Python3 should be installed__

```
yum install python3
```

__update aws instance ip in all files using this command__


```
cd /var/www/cgi-bin
sed -i 's/18.140.226.122/your_aws_ip/g' *.py
sed -i 's/18.140.226.122/your_aws_ip/g' docker/*.py
sed -i 's/18.140.226.122/your_aws_ip/g' hadoop/*.py
cd /var/www/html
sed -i 's/18.140.226.122/your_aws_ip/g' *.html
```

Restart Webserver

```
systemctl restart httpd
```




