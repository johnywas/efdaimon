# base host environment with webserver

FROM centos:latest

LABEL maintainer="efdaimon"
#Optimized service installation
RUN yum install -y epel-release && \
    yum install -y python-pip && \
    pip install --upgrade pip && \
    yum install -y httpd
RUN yum update -y
RUN echo "You visited the container website!" >> /var/www/html/index.html

EXPOSE 80

ENTRYPOINT apachectl -DFOREGROUND
