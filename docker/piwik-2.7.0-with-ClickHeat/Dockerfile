FROM tutum/apache-php

ENV PIWIK_VERSION 2.7.0

RUN rm -rf ./*
RUN mkdir tmp
RUN mkdir config
RUN curl -L -O http://builds.piwik.org/piwik-${PIWIK_VERSION}.tar.gz
RUN tar -xzf piwik-${PIWIK_VERSION}.tar.gz
RUN cp -R piwik/* ./
RUN chmod a+w tmp 
RUN chmod a+w config
RUN chmod -R 0755 /app/tmp
#RUN chmod -R 0755 /app/tmp/assets
#RUN chmod -R 0755 /app/tmp/cache
#RUN chmod -R 0755 /app/tmp/logs
#RUN chmod -R 0755 /app/tmp/tcpdf
#RUN chmod -R 0755 /app/tmp/templates_c
RUN chown -R www-data:www-data /app
RUN rm piwik-${PIWIK_VERSION}.tar.gz

RUN curl -L -O http://www.labsmedia.com/clickheat/piwik/piwik-clickheat.tar.gz
RUN tar -xzf piwik-clickheat.tar.gz
RUN mv ClickHeat /app/plugins/
RUN rm piwik-clickheat.tar.gz

EXPOSE 80
CMD ["/run.sh"]
