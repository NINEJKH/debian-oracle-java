FROM 9jkh/dotdeb:debian-jessie
MAINTAINER 9JKH Dev<dev@9jkh.co.za>

ARG DEBIAN_FRONTEND=noninteractive
ARG PACKAGE_NAME
ARG JDK_DOWNLOAD_URL
ARG REVISION

USER foobar
WORKDIR /home/foobar

RUN apt-get update -qq && apt-get -y -qq install \
  libgl1-mesa-glx \
  libgtk2.0-0 \
  libxslt1.1 \
  libxtst6 \
  libxxf86vm1

RUN wget -q "${JDK_DOWNLOAD_URL}"

RUN yes | make-jpkg \
  --full-name "9JKH (Pty) Ltd." \
  --email "dev@9jkh.co.za" \
  --revision "${REVISION}" \
  *.tar.gz \
  > /dev/null
