# syntax = docker/dockerfile:1.2

FROM centos:centos7 AS php-base

RUN yum update -y
RUN yum install -y openssh openssh-clients

COPY ./ssh2.ini /etc/php.d/ssh2.ini

ENV APP_ROOT="/var/www/app"
WORKDIR ${APP_ROOT}

ENTRYPOINT ["bash","-c"]
CMD ["/bin/bash"]