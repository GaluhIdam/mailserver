FROM debian:bullseye

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && \
    echo "postfix postfix/mailname string mail.existera.id" | debconf-set-selections && \
    echo "postfix postfix/main_mailer_type string 'Internet Site'" | debconf-set-selections && \
    apt-get install -y postfix libsasl2-modules default-mysql-client


COPY main.cf /etc/postfix/main.cf
COPY mysql-virtual-domains.cf /etc/postfix/mysql-virtual-domains.cf
COPY mysql-virtual-mailboxes.cf /etc/postfix/mysql-virtual-mailboxes.cf
COPY mysql-virtual-aliases.cf /etc/postfix/mysql-virtual-aliases.cf

CMD ["postfix", "start-fg"]
