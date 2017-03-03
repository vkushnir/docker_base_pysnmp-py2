# PySNMP docker base
Base docker image for PySNMP projects

Based on alpine linux

## Variables
- SNMP_VERSION=**2c** &mdash; snmp version 1,2c,3

*SNMP Version 1 or 2c specific*
- SNMP_COMMUNITY="**public**" &mdash; default community string

*SNMP Version 3 specific*
- SNMP_APROTOCOL="**MD5**" &mdash; default authentication protocol (**MD5**|**SHA**)
- SNMP_APASSPHRASE="**pass**" &mdash; default authentication protocol pass phrase
- SNMP_SENGINE-ID="**00000000**" &mdash; default security engine ID (e.g. 800000020109840301)
- SNMP_CENGINE-ID="**00000000**" &mdash; default context engine ID (e.g. 800000020109840301)
- SNMP_LEVEL="**noAuthNoPriv**" &mdash; default security level (**noAuthNoPriv**|**authNoPriv**|**authPriv**)
- SNMP_CONTEXT="**backup**" &mdash; default context name (e.g. bridge1)
- SNMP_USER-NAME="**backup**" &mdash; default security name (e.g. bert)
- SNMP_PPROTOCOL="**DES**" &mdash; default privacy protocol (**DES**|**AES**)
- SNMP_PPASSPHRASE="**pass**" &mdash; default privacy protocol pass phrase
- SNMP_BOOTS="" &mdash; default destination engine boots/time

## Volumes
- /usr/local/lib/python &mdash; folder for python modules
- /usr/local/share/snmp/mibs &mdash; folder for Asn1 mib modules
- /usr/local/share/snmp/pysnmp_mibs &mdash; folder for PySNMP compiled mib modules

## BUILD
    docker build source/ --tag vkushnir/pysnmp:<pysnmp version>-py<python version>
