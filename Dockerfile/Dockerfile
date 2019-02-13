# base host environment with webserver
FROM centos:latest
LABEL maintainer="yiannis"
RUN yum install -y epel-release
RUN yum install -y python-pip
RUN pip install --upgrade pip
RUN pip install docker-compose
RUN yum install -y httpd
RUN yum update -y
RUN echo "You visited the container website!" >> /var/www/html/index.html

EXPOSE 80

ENTRYPOINT apachectl -DFOREGROUND
