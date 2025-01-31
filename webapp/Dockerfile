FROM nginx 
LABEL key="LMS FRONTEND IMAGE"
RUN mkdir /frontend
WORKDIR /frontend
COPY . /frontend
RUN npm install
RUN npm build
COPY . /usr/share/nginx/html
