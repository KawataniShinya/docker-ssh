# syntax = docker/dockerfile:1.2

FROM amazonlinux:2

RUN yum update -y
RUN yum install -y openssh-server openssh-clients

RUN echo "root:root" | chpasswd
COPY ./sshd_config /etc/ssh/sshd_config
RUN ssh-keygen -A

ENV APP_ROOT="/var/www/app"
WORKDIR ${APP_ROOT}

WORKDIR ${APP_ROOT}
ENTRYPOINT ["bash","-c","/usr/sbin/sshd && /bin/bash"]
CMD [""]