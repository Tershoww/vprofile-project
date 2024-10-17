FROM mysql:8.0.33
LABEL "Project"="Vprofile"
LABEL "Author"="Tershoww"

ENV MYSQL_ROOT_PASSWORD = "salut123"
ENV MYSQL_DATABASE="accounts"

ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql