# Documentation of the first task.
## Deployment of a static website on AWS EC2 Instance using Nginx web server.
## components of the project are:
1.**EC2 instance**: An Ec2 instance is a virtual machime provided by AWS in this project I will make use Red Hat Enterprise Linux from aws.

2.**NGINX**: Nginx (pronounced "engine-x") is a high-performance web server that can also be used as a reverse proxy, load balancer, and HTTP cache. It is known for its stability, rich feature set, simple configuration, 
and low resource consumption. Here's a brief guide to help you get started with Nginx.

3.**A static website template**: I will download a simple HTML and CSS code online for our website.
## STEP 1- Set up an EC2 instance on AWS.

1. **Launch an EC2 Instance**: 
   - Sign in to the AWS Management Console.
   - Navigate to EC2 Dashboard.
   - Click on "Launch Instance" and choose Ubuntu Server 20.04 LTS as the operating system.

2. **Configure Instance Details**:
   - Choose instance type, network, subnet, and other settings as per your requirements.

3. **Add Storage**:
   - Allocate storage space according to your needs.

4. **Add Tags**:
   - Optionally, add tags for better organization.


5. **Configure Security Group**:
   - Create a new security group or use an existing one.
   - Allow inbound traffic on ports 80 (HTTP), 22 (SSH), and 443 (HTTPS) from your IP address.
 

6. **Review and Launch**:
   - Review the configuration and launch the instance.

    

7. **Connect to the Instance**:
   - Use Windows terminal to connect to the instance via SSH.
   - ![Screenshot (317)](https://github.com/highbee2810/HNG_INTERNSHIP/assets/155490206/33d4aa40-076c-497a-89ce-b5168d0f4c82)
  
## STEP 2- Install and configure Nginx web server
1.  **update the package of your server**
```
sudo yum update -y
```
![Screenshot (318)](https://github.com/highbee2810/HNG_INTERNSHIP/assets/155490206/63bb74ce-dfc7-441d-98f0-bd5679eec564)


2.  **Install Nginx server**
```
sudo yum install nginx
```
![Screenshot (319)](https://github.com/highbee2810/HNG_INTERNSHIP/assets/155490206/61c67bb2-894b-4b40-8d03-9bae81f03e07)

3. **enable nginx server**
```
sudo systemctl enable nginx
```
4. **start nginx server**
```
sudo systemctl start nginx
```
5. **check nginx status**
```
sudo systemctl status nginx
```
![Screenshot (320)](https://github.com/highbee2810/HNG_INTERNSHIP/assets/155490206/6eea21ea-707d-4723-adff-22ec8ee3dde5)

## STEP 3- Configure and upload the static website file 
**Create a directory for the website**
```
mkdir website && cd website
```
**Download a html template online**:
```
curl -o file.zip https://www.free-css.com/assets/files/free-css-templates/download/page296/little-fashion.zip
```
**Install unzip to unzip the file**
```
sudo yum install unzip && unzip file.zip
```
![Screenshot (321)](https://github.com/highbee2810/HNG_INTERNSHIP/assets/155490206/4bbe68fb-6b9c-4971-8b80-8ba2ad2b8030)

**create a directory for the website**
```
sudo mkdir /var/www/html
```
**Edit the configuration server block of nginx to reflect the path to the website /var/www/html**
```
sudo vi /etc/nginx/nginx.conf
```
![Screenshot (322)](https://github.com/highbee2810/HNG_INTERNSHIP/assets/155490206/6f5361fd-5ebe-40ae-a6f7-7065dacc1fc3)


**grant permission for nginx to access the website file**
```
sudo chown -R nginx:nginx /var/www/html
sudo chmod -R 755 /var/www/html
```
If SELinux is enforcing, it might prevent Nginx from accessing files even if file permissions are correct. Check and set the correct SELinux context:
```
sudo chcon -R -t httpd_sys_content_t /var/www/html
```
**restart nginx**
```
sudo systemctl restart nginx
```

**Using the public ip-address the website is accessible**
```
54.85.212.29
```

![Screenshot (325)](https://github.com/highbee2810/HNG_INTERNSHIP/assets/155490206/fb8eff77-63b1-4a9c-acbe-b294b9b13622)

# Conclusion:  
This project aimed to deploy a static website on ec2 instance using nginx web server, I successfully hosted a static website template i downloaded and edited part of the html code. Key findings include configuration of nginx server and granting permission to access the website file, which helps to serve the website content.
Reflecting on the project, I encountered challenges in specifying the partto the website file while configuring nginx but effectively addressed them by using pwd to know the present directory i am working on.
In conclusion, the project has achieved deployment of static website on Ec2 and provided valuable insights into web server configuration.



