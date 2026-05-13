# use this empty Dockerfile to build your assignment

# You should use the `node` official image, with the alpine 6.x branch (`node:6-alpine`)
FROM node:6-alpine

# It should use the alpine package manager to install tini: `apk add --no-cache tini`
RUN apk add --no-cache tini

# It should create directory /usr/src/app for app files
WORKDIR /usr/src/app

# Node.js uses a "package manager", so it needs to copy in package.json file
COPY package.json package.json

# It needs to run 'npm install' to install dependencies from that file and To keep it clean and small, run `npm cache clean --force` after the above, in the same RUN command
RUN npm install && npm cache clean --force

# This app listens on port 3000
EXPOSE 3000

# It needs to copy in all files from current directory into the image
COPY . .

# It needs to start the container with the command `/sbin/tini -- node ./bin/www`
CMD ["/sbin/tini", "--", "node", "./bin/www"]

