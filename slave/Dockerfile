FROM osixia/openldap:latest

RUN test -f /container/service/slapd/assets/config/replication/replication-enable.ldif \
 && test -f /container/service/slapd/startup.sh

COPY replication-enable.ldif /container/service/slapd/assets/config/replication/
COPY startup.sh.patch /container/service/slapd/

RUN apt update \
 && apt install patch \
 && cd /container/service/slapd/ \
 && patch -p1 startup.sh <startup.sh.patch \
 && apt-get purge --yes --auto-remove patch \
 && apt-get clean && rm -rf /var/lib/apt/lists/* \
