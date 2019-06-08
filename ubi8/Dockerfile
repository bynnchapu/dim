FROM registry.access.redhat.com/ubi8/ubi:latest
LABEL maintainer "Noriki Nakamura <bynn_chapu@tencho-lab.net>"

ARG USER_NAME=bynn_chapu

RUN rm -f /etc/localtime && ln -fs /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

RUN yum install -y wget less git vim sudo ncurses

RUN useradd ${USER_NAME} && usermod -aG wheel ${USER_NAME}
RUN echo "${USER_NAME} ALL=NOPASSWD: ALL" >> /etc/sudoers
WORKDIR /home/${USER_NAME}
USER ${USER_NAME}
