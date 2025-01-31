FROM node:latest AS builder
RUN mkdir /frontend
WORKDIR /frontend
COPY . /frontend
RUN npm install
RUN npm run build
EXPOSE 80
FROM nginx
COPY --from=builder /frontend/dist /usr/share/nginx/html