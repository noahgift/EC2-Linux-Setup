# EC2-Linux-Setup

[YouTube Walkthrough Here](https://www.youtube.com/watch?v=HZIG4Kwnrs4&feature=youtu.be)

1.  Setup PEM key
2.  Create security group to allow:  22 and 80
3.  Upload to Cloud9
4.  Request spot instance and launch
5.  Install http

```
sudo yum update -y
sudo yum install -y httpd
sudo systemctl start httpd
```

6.  Test out webservice

(Optional fix file permissions and add content)

```
sudo usermod -a -G apache ec2-user
sudo chown -R ec2-user:apache /var/www
# add group write permssions 
sudo chmod 2775 /var/www && find /var/www -type d -exec sudo chmod 2775 {} \;
find /var/www -type f -exec sudo chmod 0664 {} \;
```

### Amazon References

* https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-lamp-amazon-linux-2.html
