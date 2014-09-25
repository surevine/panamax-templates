FROM tutum/apache-php

ENV PIWIK_VERSION 2.6.1

RUN rm -rf ./*
RUN mkdir -p /app/tmp
RUN mkdir -p /app/config
RUN curl -L -O http://builds.piwik.org/piwik-${PIWIK_VERSION}.tar.gz
RUN tar -xzf piwik-${PIWIK_VERSION}.tar.gz
RUN chmod a+w /app/tmp && \
    chmod a+w /app/config

EXPOSE 80
CMD ["/run.sh"]
