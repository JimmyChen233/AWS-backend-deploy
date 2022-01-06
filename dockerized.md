# 1. Git clone the repository
```
git clone git@bitbucket.org:6666offers/apis.git
cd apis
```

# 2. Write dockerfile
Create a new file named "Dockerfile"
```
FROM node:14-alpine
RUN apk add --no-cache nodejs npm

WORKDIR /app
ENV PATH /app/node_modules/.bin:$PATH
# Install app dependencies
COPY package*.json /app
RUN npm install
# If you are building your code for production
# RUN npm ci --only=production

COPY . /app

EXPOSE 8081

CMD ["npm", "start"]
```
Create antoher file named ".dockerignore"
```
.pem
.gitignore
README.md
Dockerfile.prod
node_modules
npm-debug.log
node_modules
```
# 3. Build the docker image
```
docker build -t bypassj2-apis:latest .
```
![image](https://user-images.githubusercontent.com/57895489/148267947-c7aa64fe-8810-43d0-a0ac-eae99fe73810.png)

Run ```docker images``` now and you should see the image you just created. Copy its image id.

Now you should be able to run your app on local docker using ```docker run -it -p 80:8081 3ffa65c93053```

# 4. Push the image to ECR
**Create a repository on ECR**
![image](https://user-images.githubusercontent.com/57895489/148268721-f95e017d-8c14-4681-8684-618765daeabb.png)
**Copy repository URI**
![image](https://user-images.githubusercontent.com/57895489/148268861-49b240fd-8a39-47bd-a466-d8c43c4fbb63.png)
**Then use aws cli to push image**
```
// login to ecr
aws ecr get-login-password | docker login --username AWS --password-stdin 325660384969.dkr.ecr.ap-southeast-2.amazonaws.com/bypassj2-backend
// tag the image
docker tag bypassj2-apis:latest 325660384969.dkr.ecr.ap-southeast-2.amazonaws.com/bypassj2-backend
//push thge image
docker push 325660384969.dkr.ecr.ap-southeast-2.amazonaws.com/bypassj2-backend
```
**Now the latest built image is in your repository**
![image](https://user-images.githubusercontent.com/57895489/148270053-bcfb0dc2-dfc9-42f7-a1ba-2e6485804c1a.png)

