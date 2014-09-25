FROM tutum/apache-php

ENV PIWIK_VERSION 2.6.1

RUN rm -rf ./*
RUN mkdir tmp
RUN mkdir config
RUN curl -L -O http://builds.piwik.org/piwik-${PIWIK_VERSION}.tar.gz
RUN tar -xzf piwik-${PIWIK_VERSION}.tar.gz
RUN cp -R piwik/* ./
RUN pwd
RUN ls -la
RUN chmod a+w tmp 
RUN chmod a+w config
RUN chmod -R 0755 /app/tmp
#RUN chmod -R 0755 /app/tmp/assets
#RUN chmod -R 0755 /app/tmp/cache
#RUN chmod -R 0755 /app/tmp/logs
#RUN chmod -R 0755 /app/tmp/tcpdf
#RUN chmod -R 0755 /app/tmp/templates_c
RUN chown -R www-data:www-data /app

EXPOSE 80
CMD ["/run.sh"]
