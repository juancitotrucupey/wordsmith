FROM postgres
RUN mkdir -p /docker-entrypoint-initdb.d
COPY words.sql /docker-entrypoint-initdb.d
ENV POSTGRES_USER=wordsmith
ENV POSTGRES_HOST_AUTH_METHOD=trust

