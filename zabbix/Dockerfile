FROM ubuntu:24.04

RUN apt update && \
    apt install -y apache2 wget && \
    wget https://cdn.zabbix.com/zabbix/binaries/stable/7.0/7.0.7/zabbix_agent-7.0.7-linux-3.0-amd64-static.tar.gz && \
    tar -xvzf zabbix_agent-7.0.7-linux-3.0-amd64-static.tar.gz -C /usr/local/bin/ && \
    rm zabbix_agent-7.0.7-linux-3.0-amd64-static.tar.gz && \
    apt clean

COPY zabbix_agentd.conf /etc/zabbix/zabbix_agentd.conf

EXPOSE 80 10050

CMD ["apache2ctl", "-D", "FOREGROUND"]
