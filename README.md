# openldap-masterslave-container
Containers to initialize an OpenLDAP infrastructure with master-slave replication.

Based on osixia/openldap image: https://github.com/osixia/docker-openldap

Slave containers must set the following environment variables to enable replication:

 - `LDAP_REPLICATION=true`.
 - `LDAP_RID=XYZ`: Unique for each slave container. X, Y and Z are digits from 0 to 9.
 - `LDAP_REPLICATION_MASTER`: URI of the master container.
