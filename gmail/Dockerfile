FROM node:14-slim

RUN mkdir -p /usr/src/app
RUN apt-get update \  
    && apt-get install cron -y \
    && apt-get install vim -y
COPY ./cronjob /etc/cron.d/container_cronjob
COPY ./start.sh /start.sh
RUN chmod +x /start.sh

CMD [ "/bin/bash", "-c", "/start.sh && chmod 644 /etc/cron.d/container_cronjob && cron && tail -f /var/log/cron.log"]
