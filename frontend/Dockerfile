# node based image with alpine linux
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

# build the production application
RUN npm run build

# serve built files from nginx
FROM nginx:alpine
COPY --from=0 /app/dist /usr/share/nginx/html

# expose port 80
EXPOSE 80

# start nginx server
CMD ["nginx", "-g", "daemon off;"]