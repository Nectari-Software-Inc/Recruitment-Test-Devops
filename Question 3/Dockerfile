FROM mcr.microsoft.com/mssql/server:2019-latest

USER root
EXPOSE 1433:1433

WORKDIR /opt/mssql-tools/bin/
RUN ln -s /opt/mssql-tools18/bin/sqlcmd /opt/mssql-tools/bin/

RUN mkdir -p /var/opt/mssqql/docker
WORKDIR /var/opt/mssql/docker

COPY . /var/opt/mssql/docker/

RUN chmod +x /var/opt/mssql/docker/restore_db.sh
RUN chmod +x /var/opt/mssql/docker/entrypoint.sh

ENV SA_PASWWORD="Nectari2026!"
ENV ACCEPT_EULA=Y
ENV MSSQL_AGENT_ENABLED=true
ENV MSSQL_PID=Express

ENTRYPOINT [ "./entrypoint.sh" ]
