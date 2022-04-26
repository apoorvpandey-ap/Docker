From quay.io/wildfly/wildfly:26.0.0.Final

COPY mysql-ds.xml /opt/jboss/wildfly/standalone/deployments
COPY vdoxx.ear /opt/jboss/wildfly/standalone/deployments
COPY standalone.xml /opt/jboss/wildfly/standalone/configuration
COPY mgmt-users.properties /opt/jboss/wildfly/standalone/configuration
COPY mgmt-groups.properties /opt/jboss/wildfly/standalone/configuration
COPY application-users.properties /opt/jboss/wildfly/standalone/configuration
COPY application-roles.properties /opt/jboss/wildfly/standalone/configuration

RUN mkdir -p  /opt/jboss/wildfly/modules/system/layers/base/com/postgres/main
RUN mkdir -p  /opt/jboss/wildfly/modules/system/layers/base/com/oracle/main
RUN mkdir -p  /opt/jboss/wildfly/modules/system/layers/base/com/mysql_8/main
RUN mkdir -p  /opt/jboss/wildfly/modules/system/layers/base/com/mysql/main
RUN mkdir -p  /opt/jboss/wildfly/modules/system/layers/base/com/mssql_2017_microsoft_driver/main
RUN mkdir -p  /opt/jboss/wildfly/modules/system/layers/base/com/mssql_2017/main
RUN mkdir -p  /opt/jboss/wildfly/modules/system/layers/base/com/mssql/main


COPY postgres/main/ /opt/jboss/wildfly/modules/system/layers/base/com/postgres/main
COPY oracle/main /opt/jboss/wildfly/modules/system/layers/base/com/oracle/main
COPY mysql_8/main/ /opt/jboss/wildfly/modules/system/layers/base/com/mysql_8/main
COPY mysql/main /opt/jboss/wildfly/modules/system/layers/base/com/mysql/main
COPY mssql_2017_microsoft_driver/main /opt/jboss/wildfly/modules/system/layers/base/com/mssql_2017_microsoft_driver/main
COPY mssql_2017/main /opt/jboss/wildfly/modules/system/layers/base/com/mssql_2017/main
COPY mssql/main /opt/jboss/wildfly/modules/system/layers/base/com/mssql/main

RUN ls -l  /opt/jboss/wildfly/modules/system/layers/base/com/mysql_8/main

EXPOSE 3306

CMD ["/opt/jboss/wildfly/bin/standalone.sh", "-b", "0.0.0.0"]
