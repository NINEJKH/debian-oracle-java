FROM 9jkh/dotdeb:ubuntu-xenial
MAINTAINER 9JKH Dev<dev@9jkh.co.za>

ARG DEBIAN_FRONTEND=noninteractive
ARG PACKAGE_NAME
ARG JDK_DOWNLOAD_URL

# install packages
RUN apt-get update -qq && apt-get -y -qq install \
  ca-certificates \
  java-package \
  java-common \
  libgl1-mesa-glx \
  libxtst6 \
  libxxf86vm1

USER foobar
WORKDIR /home/foobar

RUN wget -q "${JDK_DOWNLOAD_URL}"

RUN yes | make-jpkg \
  --full-name "9JKH (Pty) Ltd." \
  --email "ftpmaster@9jkh.co.za" \
  *.tar.gz \
  > /dev/null
