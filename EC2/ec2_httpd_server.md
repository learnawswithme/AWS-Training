# EC2 instance simple HTTP server setup

This doc contains the code for setiting up http server on EC2 instance

Run the below command 1 by 1 

```
yum update -y
yum install -y httpd.x86_64
systemctl start httpd.service
systemctl enable httpd.service
echo "Hello World from $(hostname -f)" > /var/www/html/index.html
```


## What are the steps followed above

- Update the EC2 instance with required softwares
- Install HTTP server on EC2 instance
- Start http service
- Enable http service
- Add a dummy line into index.htlm which will be displayed on the service.


## Advanced EC2 user data 

For automating of this using EC2 userdata we can do this below : 

```
#!/bin/bash
yum update -y
yum install -y httpd.x86_64
systemctl start httpd.service
systemctl enable httpd.service
echo "Hello World from $(hostname -f)" > /var/www/html/index.html
```

