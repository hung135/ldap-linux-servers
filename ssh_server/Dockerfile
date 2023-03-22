FROM ubuntu:20.04

RUN apt-get update && \
    apt-get install -y openssh-server ldap-utils libnss-ldap libpam-ldap nscd vim && \
    mkdir /var/run/sshd && \
    echo 'root:root' | chpasswd

COPY ldap.conf /etc/ldap/ldap.conf
COPY nsswitch.conf /etc/nsswitch.conf
COPY common-session /etc/pam.d/common-session

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]

