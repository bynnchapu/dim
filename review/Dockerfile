FROM vvakame/review:3.2
LABEL maintainer "Noriki Nakamura <bynn_chapu@tencho-lab.net>"

ARG USER_NAME=bynn_chapu

RUN apt update

RUN apt install locales
RUN locale-gen ja_JP.UTF-8
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:en
ENV LC_ALL ja_JP.UTF-8
RUN rm -f /etc/localtime && ln -fs /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

RUN apt install -y sudo vim less

RUN adduser ${USER_NAME}
RUN echo "${USER_NAME} ALL=NOPASSWD: ALL" >> /etc/sudoers
WORKDIR /home/${USER_NAME}
USER ${USER_NAME}
