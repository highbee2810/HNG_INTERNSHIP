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




