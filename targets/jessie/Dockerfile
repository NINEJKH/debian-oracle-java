FROM 9jkh/dotdeb:debian-jessie
MAINTAINER 9JKH Dev<dev@9jkh.co.za>

ARG \
  DEBIAN_FRONTEND=noninteractive \
  PACKAGE_NAME \
  JDK_DOWNLOAD_URL \
  REVISION

USER foobar
WORKDIR /home/foobar

RUN wget -q "${JDK_DOWNLOAD_URL}"

RUN yes | make-jpkg \
  --full-name "9JKH (Pty) Ltd." \
  --email "dev@9jkh.co.za" \
  --with-system-certs \
  --revision "${REVISION}" \
  *.tar.gz \
  > /dev/null
