# AWS-backend-deploy

# 1. launch an instance
I choose ubuntu here.
No need to change default settings. Skip to step 6
![image](https://user-images.githubusercontent.com/57895489/147891540-d14956f0-5c92-411d-8272-ef791495edd0.png)

# 2. set up ec2
**connect to ec2 instance on terminal**
![image](https://user-images.githubusercontent.com/57895489/147892743-6ef016b0-0703-4c90-bed4-55aa040cd0b4.png)
**Install nodejs**

curl -fsSL https://deb.nodesource.com/setup_14.x | sudo -E bash -

sudo apt-get install -y nodejs

**Install git**

sudo apt-get install git

**Clone repository**
![Uploading image.png…]()

**Redirect port 80 to 8081**

sudo iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-ports 8081

**Run server on ec2**

cd apis

npm install

node app

**Keep App running using pm2**

sudo npm install pm2 -g

pm2 start app.js

**Automatically run PM2 when the server restarts**

sudo pm2 startup
