FROM osixia/openldap:latest

RUN test -f /container/service/slapd/assets/config/replication/replication-enable.ldif
COPY replication-enable.ldif /container/service/slapd/assets/config/replication/
