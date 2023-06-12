FROM postgres:14.1-alpine

ENV POSTGRES_DB=db \
   POSTGRES_USER=usr \
   POSTGRES_PASSWORD=pwd

COPY CreateScheme.sql /docker-entrypoint-initdb.d/
COPY InsertData.sql /docker-entrypoint-initdb.d/

# RUN psql -U "$POSTGRES_USER" -d "$POSTGRES_DB" -f /CreateScheme.sql
# RUN psql -U "$POSTGRES_USER" -d "$POSTGRES_DB" -f /InsertData.sql