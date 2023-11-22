FROM gcr.io/google.com/cloudsdktool/google-cloud-cli:latest

RUN URL="https://storage.googleapis.com/cloud-sql-connectors/cloud-sql-proxy/v2.6.1" && \
    curl "$URL/cloud-sql-proxy.linux.amd64" -o cloud-sql-proxy &&\
    chmod +x cloud-sql-proxy &&\
    mv cloud-sql-proxy /usr/bin

ENTRYPOINT cloud-sql-proxy -p 5432 -a 0.0.0.0 $DB_INSTANCE  #vivihealth-staging:us-central1:vivihealth-staging-db
