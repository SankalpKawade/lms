# base image from which, to create our custom image
# marking this stage as multi-build
FROM node:latest AS builder
# creating a folder in contianer
RUN mkdir /frontend
# making it as a working directory
WORKDIR /frontend
# copying all the files from current folder to container folder
COPY . /frontend
# run and build commands
RUN npm install
RUN npm run build

# using above build to copy the dist folder to nginx root dirrectory
FROM nginx
COPY --from=builder /frontend/dist /usr/share/nginx/html