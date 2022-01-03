# AWS-backend-deploy

# 1. launch an instance
![image](https://user-images.githubusercontent.com/57895489/147891430-2279f97a-c20a-41f7-9c63-47befb8526be.png)
No need to change default settings. Skip to step 6
![image](https://user-images.githubusercontent.com/57895489/147891540-d14956f0-5c92-411d-8272-ef791495edd0.png)

# 2. set up ec2
**connect to ec2 instance on terminal**
![image](https://user-images.githubusercontent.com/57895489/147892743-6ef016b0-0703-4c90-bed4-55aa040cd0b4.png)
**run: sudo yum update -y**
![image](https://user-images.githubusercontent.com/57895489/147892776-8df33ea3-052d-42f3-85fb-a79be4dbb65c.png)
**use curl to install nvm**

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash

**exit and reopen ec2 instance to check nvm install**
![image](https://user-images.githubusercontent.com/57895489/147892892-d673e4e3-a75f-4513-95ed-7c201f70f1ad.png)
**Install node**
![image](https://user-images.githubusercontent.com/57895489/147892929-62cd3d38-13c2-4f41-9cc9-4bf83bce1091.png)
**Install git**
sudo yum install git -y
**Clone repository**
![Uploading image.png…]()
**Redirect port 80 to 8081**
sudo iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-ports 8081
**Run server on ec2**
npm install
node app
**Keep App running using pm2**
npm install pm2 -g
pm2 start app.js
**Automatically run PM2 when the server restarts**
