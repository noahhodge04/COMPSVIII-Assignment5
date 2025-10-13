# node js image with alpine linux
FROM node:18-alpine

# set working directory
WORKDIR /app

# copy package.json and package-lock.json
COPY package.json ./
COPY package-lock.json ./

# install dependencies
RUN npm install

# copy all files
COPY . .

# create data directory for SQLite
RUN mkdir -p /app/data

# expose port 5000
EXPOSE 5000

# start the application
CMD ["npm", "start"]