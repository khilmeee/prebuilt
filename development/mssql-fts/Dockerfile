FROM mcr.microsoft.com/mssql/server:2022-latest

USER root

RUN apt update && \
    apt-get install -yq gnupg gnupg2 gnupg1 curl apt-transport-https \
    && curl https://packages.microsoft.com/keys/microsoft.asc -o /var/opt/mssql/ms-key.cer \
    && apt-key add /var/opt/mssql/ms-key.cer \
    && curl https://packages.microsoft.com/config/ubuntu/22.04/mssql-server-2022.list -o /etc/apt/sources.list.d/mssql-server-2022.list \
    && apt-get update && apt-get install -y mssql-server-fts \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists

USER mssql