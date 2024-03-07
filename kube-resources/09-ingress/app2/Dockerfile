FROM almalinux:8
RUN yum install nginx -y
RUN rm -rf /usr/share/nginx/html/index.html
RUN echo "<h1>Hello, I am from APP-2</h1>" > /usr/share/nginx/html/index.html
CMD ["nginx", "-g", "daemon off;"]

# docker build -t satishkalari/app2:v1 
# docker push satishkalari/app2:v1