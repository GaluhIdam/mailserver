FROM debian:bullseye

RUN apt-get update && apt-get install -y postfix libsasl2-modules mysql-client

COPY main.cf /etc/postfix/main.cf
COPY mysql-virtual-domains.cf /etc/postfix/mysql-virtual-domains.cf
COPY mysql-virtual-mailboxes.cf /etc/postfix/mysql-virtual-mailboxes.cf
COPY mysql-virtual-aliases.cf /etc/postfix/mysql-virtual-aliases.cf

CMD ["postfix", "start-fg"]
