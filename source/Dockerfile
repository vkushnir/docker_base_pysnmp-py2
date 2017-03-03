FROM alpine:latest
MAINTAINER Vladimir Kushnir <vkushnir@gmail.com>

LABEL description="Base docker image for PySNMP projects"

ENV \
    SNMP_VERSION=2c \
    SNMP_COMMUNITY="public" \
    SNMP_APROTOCOL="MD5" \
    SNMP_APASSPHRASE="pass" \
    SNMP_SENGINE-ID="00000000" \
    SNMP_CENGINE-ID="00000000" \
    SNMP_LEVEL="noAuthNoPriv" \
    SNMP_CONTEXT="backup" \
    SNMP_USER-NAME="backup" \
    SNMP_PPROTOCOL="DES" \
    SNMP_PPASSPHRASE="pass" \
    SNMP_BOOTS_TIME="" \
    PYTHONPATH="/usr/local/lib/python"

RUN apk update && apk upgrade && \
    apk del --purge rsyslog

RUN rm -f /var/log/* /sbin/rsyslogd && \
    apk add --no-cache --update python2 py2-pip py2-snmp

RUN pip install --upgrade pip && \
    pip install pysmi pysnmp_mibs pysnmp_apps

RUN rm /var/cache/apk/*

VOLUME \
    /usr/local/bin \
    /usr/local/lib/python \
    /usr/local/share/snmp/mibs \
    /usr/local/share/snmp/pysnmp_mibs

ENTRYPOINT ["python"]

