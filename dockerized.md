# 1. Git clone the repository
'''
git clone git@bitbucket.org:6666offers/apis.git
cd apis
'''

# 2. Write dockerfile
'''
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
'''

