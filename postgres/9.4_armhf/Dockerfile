FROM resin/armv7hf-debian-qemu
MAINTAINER Jimmy Yang <gankkank@gmail.com>

RUN [ "cross-build-start" ]

RUN apt-get update && \
  apt-get install -y nginx git vim

RUN apt-get update \
  && apt-get install postgresql-9.4 locales ca-certificates wget -y

RUN localedef -i en_US -c -f UTF-8 -A  /etc/locale.alias en_US.UTF-8

ADD https://github.com/tianon/gosu/releases/download/1.7/gosu-armhf /usr/sbin/gosu

RUN chmod +x /usr/sbin/gosu

ENV LANG en_US.utf8

# Clean up APT
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENV PG_MAJOR 9.4
ENV PATH /usr/lib/postgresql/$PG_MAJOR/bin:$PATH
ENV PGDATA /var/lib/postgresql/data
VOLUME /var/lib/postgresql/data

COPY docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]

EXPOSE 5432
CMD ["postgres"]

RUN [ "cross-build-end" ]  
