FROM almalinux:8
RUN yum install nginx -y
RUN rm -rf /usr/share/nginx/html/index.html
RUN echo "<h1>Hello, I am from APP-1</h1>" > /usr/share/nginx/html/index.html
CMD ["nginx", "-g", "daemon off;"]

# docker build -t satishkalari/app1:v1 
# docker login
# docker push satishkalari/app1:v1