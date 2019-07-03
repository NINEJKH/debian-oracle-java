FROM 9jkh/dotdeb:debian-buster
MAINTAINER 9JKH Dev<dev@9jkh.co.za>

ARG DEBIAN_FRONTEND=noninteractive
ARG PACKAGE_NAME
ARG JDK_DOWNLOAD_URL
ARG REVISION

RUN apt-get -qq update && apt-get -y -qq install \
      libgtk-3-0

USER foobar
WORKDIR /home/foobar

RUN sed 's/override_dh_strip_nondeterminism:/override_dh_builddeb:\n\tdh_builddeb -- --no-uniform-compression\n\n\0/' /usr/share/java-package/javase.sh

RUN wget -q "${JDK_DOWNLOAD_URL}"

RUN yes | make-jpkg \
  --full-name "9JKH (Pty) Ltd." \
  --email "dev@9jkh.co.za" \
  --with-system-certs \
  --revision "${REVISION}" \
  *.tar.gz \
  > /dev/null
