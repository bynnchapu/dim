FROM centos:7
LABEL maintainer "Noriki Nakamura <bynn_chapu@tencho-lab.net>"

ARG USER_NAME=bynn_chapu

RUN localedef -vc -i ja_JP -f UTF-8 ja_JP.UTF-8; true
ENV LANG=ja_JP.UTF-8
RUN rm -f /etc/localtime && ln -fs /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

RUN yum install -y wget less git vim sudo

RUN useradd ${USER_NAME} && usermod -aG wheel ${USER_NAME}
RUN echo "${USER_NAME} ALL=NOPASSWD: ALL" >> /etc/sudoers
WORKDIR /home/${USER_NAME}
USER ${USER_NAME}
